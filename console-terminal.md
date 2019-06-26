# Console / Terminal Cheatsheet

Index:
* [Create a new empty file from terminal](#create-a-new-empty-file)
* [Open url](#open-url)
* [path linux style in windows](#path-linux-style-in-windows)
* [Start new node project](#start-new-node-project)

------
## <a name="create-a-new-empty-file"></a> Create a new empty file from terminal
Linux:
```
touch index.js
```
Windows:
```
break > new-emty-file.txt
```
------
## <a name="open-url"></a> Open url
Windows:
```
start "" "http://www.google.com"
```
------
## <a name="path-linux-style-in-windows"></a> path linux style in windows
Windows uses backslashes (\) as folder separator in paths. So you can't use linux style (slash "/") in windows commands. You can use string replace to replaces it in the command line:
```
SET a=code/uploads/temp/temp.csv & del %a:/=\%
```
------
## <a name="start-new-node-project"></a> Start new node project
Windows:
```
git init && echo node_modules>.gitignore && break>index.js && npm init -y
```
You might be needing to start an Express server. In that case: [Patooverflow's Express starter](https://github.com/patopitaluga/patooverflow/blob/master/node-javascript.md#express-hello-world-starter)
