# Configuring your Windows development environment

## Command line console and other useful tools

Software | Description
-------- | -------
cmd | CLI
PowerShell | `choco install powershell`
[Chocolatey](https://chocolatey.org/) | `@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin`
[Git](https://git-for-windows.github.io/) | `choco install git`
[nvm-windows](https://github.com/coreybutler/nvm-windows) | A node.js version management utility
[npm-windows-upgrade](https://github.com/felixrieseberg/npm-windows-upgrade) | `npm install npm-windows-upgrade -g`
terminal emulators | [cmder](http://cmder.net/) and [ConEmu](https://conemu.github.io/)
[Cygwin](http://cygwin.com/index.html) | Get that Linux feeling
[Putty](http://www.putty.org/) | ssh client
[WinSCP](https://winscp.net/eng/index.php) | free [S]FTP client, also supports SCP and webDAV
[Fiddler](http://www.telerik.com/fiddler) | a web debugging tool. In general, people use it for the browser-side debugging, but you can also [configure](http://stackoverflow.com/questions/8697344/can-a-proxy-like-fiddler-be-used-with-node-jss-clientrequest) it to view server-side requests from Node.js

## Editors and IDEs

Software | Description
-------- | -------
[Sublime Text](http://www.sublimetext.com/) | `choco install sublimetext3`
[Notepad++](https://notepad-plus-plus.org/) | `choco install notepadplusplus`
[Visual Studio Code](https://code.visualstudio.com/) | `choco install visualstudiocode`

## MAX_PATH explanation and workarounds

- Start in a short path (e.g. `c:\src`)
- `> npm install -g rimraf` delete files that exceed max_path
- `> npm dedupe` moves duplicate packages to top-level
- `> npm install -g flatten-packages` moves all packages to top-level, but can cause versioning issues
- Upgrade to npm@3 which attempts to the make the `node_modules` folder heirarchy maximally flat
  - Ships with Node v5
  - Or… `> npm install –g npm-windows-upgrade`
- Future
  - .NET file APIs
    - [The plan](https://www.youtube.com/watch?v=lpa2OFauASM)
    - [Progress](https://github.com/dotnet/corefx/issues/645)

## Compiling native Addon modules

### Environment setup and configuration

#### Prerequisites

##### 0. [Node.js](https://nodejs.org/) - `choco install nodejs`

##### 1. Visual C++ Build Environment:

- Option 1: Install [Visual C++ Build Tools](http://go.microsoft.com/fwlink/?LinkId=691126) using the __Default Install__ option.

- Option 2: Install [Visual Studio 2015](https://www.visualstudio.com/products/visual-studio-community-vs) (or modify an existing installation) and select Common Tools for Visual C++ during setup. This also works with the free Community and Express for Desktop editions.

> [Windows Vista / 7 only] requires [.NET Framework 4.5.1](http://www.microsoft.com/en-us/download/details.aspx?id=40773)

##### 2. [Python](https://www.python.org/)

```cmd
choco install python2
npm config set python python2.7
```

##### 3. `npm config set msvs_version 2015`

#### Verify everything's working

- bson
- bufferutil
- kerberos
- node-sass
- sqlite3
- phantomjs
- utf-8-validate

## [XAMPP](https://www.apachefriends.org/index.html) - PHP development environment
