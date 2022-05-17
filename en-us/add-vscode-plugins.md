## Add build-in config

Add or update the properties in your `package.json`, the sample is add python plugins in follow:
```
{
  "scripts": {
    ...
    "prepare": "lerna run prepare && yarn download:plugins",
    "download:plugins": "theia download:plugins",
    ...
  },
  "theiaPluginsDir": "plugins",
  "theiaPlugins": {
    "vscode-builtin-python": "https://open-vsx.org/api/vscode/python/1.62.3/file/vscode.python-1.62.3.vsix",
    "vscode-python": "https://open-vsx.org/api/ms-python/python/2022.2.1924087327/file/ms-python.python-2022.2.1924087327.vsix",
    "vscode-magic-python": "https://open-vsx.org/api/magicstack/MagicPython/1.1.1/file/magicstack.MagicPython-1.1.1.vsix"
  },
}
```

The follow properties are used to consume builtin plugins.
`theiaPluginsDir`: the relative path to download plugins into


The vscode plugins https://open-vsx.org/

> NOTE: Please don't try use the vscode extension URL, it's only be used in vscode. 

## Download plugins

Use the download script previous added in package.json.

    > yarn download:plugins

> WARNING: If you are the 'One', download will be very very slowly, even though apply proxy. Please sit and relax.

The download command not support auto update plugins, it will verifies the identifier(folder name in 'plugins'), and if it's already existed then it doesn't attempt to re-download the extensions. 

If you want update extensions, then you should delete the extensions folder in 'plugins', running download command again.

## Troubleshooting

### 1. Failed download plugins by command

The way that open the plugin url in browser and download it, manual unzip the .vsix file in local. 

Your need to rename the folder to the name what you designed in theiaPlugins, then copy to the 'plugins' folder, done.