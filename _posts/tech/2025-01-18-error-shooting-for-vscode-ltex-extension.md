---
layout: post
title: VS Code LTeX 扩展在 LaTeX 配置中无法使用 Java 运行
category: 技术
tags: vscode
keywords: LTex extension, LaTex, Java
description: 
---


## 问题描述

在 Visual Studio Code 的 LaTeX 配置中使用 LTeX 扩展时，打开包含 LaTeX 文档的文件夹会出现如下错误提示：

> [![enter image description here](https://i.sstatic.net/Z4WjZfSm.png)](https://i.sstatic.net/Z4WjZfSm.png)

报错信息提示：
> Could not run ltex-ls with Java, please see the output panel 'LTeX Language Client' for details. You might want to try offline installation.

紧接着出现：

> [![enter image description here](https://i.sstatic.net/UmmmGvME.png)](https://i.sstatic.net/UmmmGvME.png)

以下是 LTeX 语言客户端的输出信息：

```bash
Info: Setting LTeX UI language to 'en'.
Info: Loading i18n messages...
Info: Loading default i18n messages...
Info: 
Info: ltex.ltex-ls.path not set.
Info: Searching for ltex-ls in 'c:\Users\foobar\.vscode\extensions\valentjn.vscode-ltex-13.1.0\lib'...
Info: ltex-ls found in 'c:\Users\foobar\.vscode\extensions\valentjn.vscode-ltex-13.1.0\lib\ltex-ls-15.2.0'.
Info: 
Info: Using ltex-ls from 'c:\Users\foobar\.vscode\extensions\valentjn.vscode-ltex-13.1.0\lib\ltex-ls-15.2.0'.
Info: Using Java from 'C:\Program Files\Microsoft\jdk-11.0.16.101-hotspot\bin\java.exe' (set in ltex.java.path).
Info: Testing ltex-ls...
Info:   Command: "c:\\Users\\foobar\\.vscode\\extensions\\valentjn.vscode-ltex-13.1.0\\lib\\ltex-ls-15.2.0\\bin\\ltex-ls.bat"
Info:   Arguments: ["--version"]
Info:   env['JAVA_HOME']: "C:\\Program Files\\Microsoft\\jdk-11.0.16.101-hotspot\\bin\\java.exe"
Info:   env['JAVA_OPTS']: "-Xms64m -Xmx512m"
Error: Test failed.
Error: Error details:
Error: Error: spawnSync c:\Users\foobar\.vscode\extensions\valentjn.vscode-ltex-13.1.0\lib\ltex-ls-15.2.0\bin\ltex-ls.bat EINVAL
Error:  at Object.spawnSync (node:internal/child_process:1124:20)
Error:  at Object.spawnSync (node:child_process:914:24)
Error:  at DependencyManager.<anonymous> (c:\Users\foobar\.vscode\extensions\valentjn.vscode-ltex-13.1.0\dist\extension.js:13528:45)
Error:  at Generator.next (<anonymous>)
Error:  at fulfilled (c:\Users\foobar\.vscode\extensions\valentjn.vscode-ltex-13.1.0\dist\extension.js:13159:58)
Info: ltex-ls did not print expected version information to stdout.
Info: stdout of ltex-ls:
Info: 
Info: stderr of ltex-ls:
Info: 
Info: You might want to try offline installation, see https://valentjn.github.io/vscode-ltex/docs/installation-and-usage.html#offline-installation.
```

系统中通过 Chocolatey 和 winget 安装了多个 Java 版本。运行命令 `where java` 得到如下结果：

```makefile
C:\Program Files\Eclipse Adoptium\jre-8.0.422.5-hotspot\bin\java.exe
C:\Program Files (x86)\Common Files\Oracle\Java\java8path\java.exe
C:\Program Files (x86)\Common Files\Oracle\Java\javapath\java.exe
C:\Program Files\AdoptOpenJDK\jdk-15.0.2.7-hotspot\bin\java.exe
C:\ProgramData\Oracle\Java\javapath\java.exe
C:\Program Files\Microsoft\jdk-11.0.16.101-hotspot\bin\java.exe
C:\Program Files\OpenJDK\jdk-22.0.2\bin\java.exe
```

这是我的 LaTeX 配置文件 `settings.json`：

```json
{
    "editor.formatOnSave": true,
    "ltex.java.path": "C:\\Program Files\\Microsoft\\jdk-11.0.16.101-hotspot\\bin\\java.exe"
}
```

## 解决方案

我参考了 tobiscode 在这篇帖子中提供的方案，成功解决了该问题：

[https://github.com/valentjn/vscode-ltex/issues/884#issuecomment-2263630384](https://github.com/valentjn/vscode-ltex/issues/884#issuecomment-2263630384)

需对 _extensions.js_ 文件进行修改，该文件位于：

```bash
%USERPROFILE%\.vscode\extensions\valentjn.vscode-ltex-13.1.0\dist
```

具体修改如下：

- 将第13516行的：

```bash
    const executableOptions = {
         encoding: 'utf-8',
         timeout: 15000,
};
```

修改为：

```yaml
    const executableOptions = {
         encoding: 'utf-8',
         timeout: 15000,
         shell: true,
};
```

- 将第13616行的：

```bash
 const executableOptions = {
         encoding: 'utf-8',
         timeout: 15000,
 };
```
 
修改为：

```yaml
 const executableOptions = {
           encoding: 'utf-8',
           timeout: 15000,
           shell: true,
       };
```

- 将第24689行的：

```dart
 const execOptions = Object.create(null);
```
 
改为：
 
```cpp
 const execOptions = {
                   shell: true
               }
```

- 将第24823行的：

```bash
 options.cwd = options.cwd || serverWorkingDir;
```

改为：

```bash
 options.cwd = options.cwd || serverWorkingDir;
       options.shell = true;
```

以上修改启用了 `shell: true` 选项，解决了 LTeX 扩展无法通过 Java 运行的问题。
