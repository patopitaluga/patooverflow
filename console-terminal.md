# Console / Terminal Cheatsheet

Index:
* [Create a new empty file from terminal](#create-a-new-empty-file)
* [path linux style in windows](#path-linux-style-in-windows)

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

## <a name="path-linux-style-in-windows"></a> path linux style in windows
Windows uses backslashes (\) as folder separator in paths. So you can't use linux style (slash "/") in windows commands. You can use string replace to replaces it in the command line:
```
SET a=code/uploads/temp/temp.csv & del %a:/=\%
```
