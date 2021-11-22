<h1 align="center">Theia cookie doc</h1>

A three-party document for enthusiasts-selft without the [Theia Project](https://github.com/eclipse-theia/theia).

[Theia: 1.18.0](https://img.shields.io/badge/Theia-1.18.0-brightgreen)
[Node: 12.22.7](https://img.shields.io/badge/Theia-1.18.0-brightgreen)
[Electron: 9.4.4](https://img.shields.io/badge/Theia-1.18.0-brightgreen)

## Navigation

[中文](./zh-cn/main.md) | English

## Resource

- [[Theia official website](https://theia-ide.org/)] is a main way to learn it, even if its access is not stable.
- [[Theia-IDE gourp](https://github.com/theia-ide)] include some theia sample project.
- [[Inversify](https://inversify.io/)] is a inversion of control container be used in Theia.
- [[React.js](https://zh-hans.reactjs.org/)] be used in Theia.
- [[phosphorjs](https://phosphorjs.github.io/)] is a UI library include Panel/Layout control & base widget control be used in Theia. It have pool doc and be archived.
- [[codicon](https://microsoft.github.io/vscode-codicons/dist/codicon.html)] Aligns button-icon css with vscode.
- (@Deprecated)[[Octicons](https://github.com/primer/octicons)] is the primary icons library be uesd in Theia.
- (@Deprecated)[[fontawesome](https://fontawesome.com/v5.15/icons?d=gallery&p=2)] is the second primary icons library be used in Theia.

## Quick start

#### 1. Create Object

> Note: Project name and file name best not use `uper case`(e.g. myApp), prevent making any unpredictable problems.

#### 2. Coding

#### 3. Dev

#### 4. Electron package 

Install dev tool `electron-builder` version 22.4.1, corresponding electron version 9.4.4, corresponding nodejs version 12.*.*

    cd ./electron-app/
    yarn add electron-builder@22.4.1 --dev

Specify the standard fields in the `electron-app/package.json`. e.g. as follow:

    {
        ...
        "name": "myAppName",
        "description": "myAppName's description.",
        "author":"author name",
        "version": "1.0.0",
        ...
        "scripts": {
            ...
            "dist": "electron-builder",
            "pack": "electron-builder --dir"
        },
        "theia": {
            "target": "electron",
            "frontend": {
            "config": {
                "applicationName": "myAppName"
            }
            },
            "backend": {
            "config": {
                "startupTimeout": -1
            }
            }
        }
    }

Create `electron-builder.yml` in electron workfolder `./electron-app` as follow:

    electron-builder.yml

    {
        appId: myAppName
        productName: myAppName
        copyright: Copyright © 2021 six&six&six Company.
        electronDist: ../node_modules/electron/dist
        electronVersion: 9.4.4

        # Theia need disable asar
        asar: false

        directories:
        buildResources: ../resources

        files:
        - src-gen
        - lib
        - package.json
        - "!**node_modules/electron/**"

        win:
        icon: ../resources/icon.ico
        target:
            - nsis

        nsis:
            menuCategory: true
            oneClick: false
            perMachine: true
            installerHeaderIcon: icon.ico
            installerIcon: icon.ico
            uninstallerIcon: icon.ico
            installerSidebar: icon.ico
            uninstallerSidebar: icon.ico
            allowToChangeInstallationDirectory: true
            runAfterFinish: false
            artifactName: ${productName}-Installer-${version}.${ext}
    }

Generate the package directory without really packaging. This is useful for testing or distrubutable `Portable version`

    yarn run pack

Package in a distributable file format.(e.g. exe, dmg, deb)

    yarn dist

## Contribute

I will add some empty chapter lists later, you can fork and edit by yourself, and then pull a request. Welcome other Theia devloper contribute your using experience.