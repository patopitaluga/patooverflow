# Visual Studio Code

On github: https://github.com/patopitaluga/patooverflow/blob/master/visual-studio-code.md

Index:
* [Configuration File](#configuration-file)
* [Useful configurations](#useful-configurations)
* [Disable suggestion on "space"](#disable-suggestion)
* [List installed plugins](#list-installed-plugins)
* [Useful plugins](#useful-plugins)
* [User snippets](#user-snippets)

------

## <a name="configuration-file"></a> Configuration File:

Press ctrl + shift + p and write settings.json will display among other options "Preferences: Open User Settings (JSON)

------

## <a name="useful-configurations"></a> Useful configurations:

Code > Preferences > Settings
```
workbench.sideBar.location
```

```
editor.minimap.enabled
```

------

## <a name="disable-suggestion"></a> Disable suggestion on "space"

```
"editor.acceptSuggestionOnCommitCharacter": false
```

------

## <a name="list-installed-plugins"></a> List installed plugins:

```
code --list-extensions
```

------

## <a name="useful-plugins"></a> Useful plugins:

- Slugify https://marketplace.visualstudio.com/items?itemName=maximerouiller.slugify-vscode
- Beautify JSON https://marketplace.visualstudio.com/items?itemName=Meezilla.json
- Live Share https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare
- Vue tooling https://marketplace.visualstudio.com/items?itemName=octref.vetur
- Copy Copy Paste https://marketplace.visualstudio.com/items?itemName=rockingskier.copy-copy-paste
- File utils (Duplicate file) https://marketplace.visualstudio.com/items?itemName=sleistner.vscode-fileutils
- Alphabetical Sorter https://marketplace.visualstudio.com/items?itemName=ue.alphabetical-sorter
- Vue Language Features (Volar) https://marketplace.visualstudio.com/items?itemName=Vue.volar

------

## <a name="user-snippets"></a> User snippets:

Code > Preferences > Configure User Snippets

```
  "Print to console": {
    "prefix": "log",
    "body": [
      "console.log('$1');",
      "$2"
    ],
    "description": "Log output to console"
  },
```


