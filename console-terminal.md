# Console / Terminal Cheatsheet

On github: https://github.com/patopitaluga/patooverflow/blob/master/console-terminal.md

Also useful:
* [Node / javascript cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/node-javascript.md)

Index:
* [Create a new empty file from terminal](#create-a-new-empty-file)
* [Delete non empty folders](#delete-non-empty-folders)
* [List files one below the other](#list-files-one-below-the-other)
* [Open bash inside container](#open-bash-inside-container)
* [Open url](#open-url)
* [path linux style in windows](#path-linux-style-in-windows)
* [Start new node project](#start-new-node-project)

------
## <a name="create-a-new-empty-file"></a> Create a new empty file from terminal
Linux:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
touch index.js
```
Windows:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
break > new-emty-file.txt
```

------
## <a name="list-files-one-below-the-other"></a> List files one below the other
Linux:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
rm -rf dir-name
```
Windows:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
rmdir /S nonemptydir
```
or without prompt
```
rmdir /Q /S nonemptydir
```

------
## <a name="delete-non-empty-folders"></a> Delete non empty folders
Linux:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
ls -1a
```
Windows:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
dir /b /a-d
```

To export the list to a file:

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
ls -1a>list.txt
```
or
```
dir /b /a-d>list.txt
```

------
## <a name="open-bash-inside-container"></a> Open bash inside container

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
docker exec -it <container name> bash
```
------
## <a name="open-url"></a> Open url
Windows:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
start "" "http://www.google.com"
```
------
## <a name="path-linux-style-in-windows"></a> path linux style in windows
Windows uses backslashes (\) as folder separator in paths. So you can't use linux style (slash "/") in windows commands. You can use string replace to replaces it in the command line:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
SET a=code/uploads/temp/temp.csv & del %a:/=\%
```
------
## <a name="start-new-node-project"></a> Start new node project
Windows:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
git init && echo node_modules>.gitignore && break>index.js && npm init -y
```
You might need to start an Express server. In that case: [Patooverflow's Express starter](https://github.com/patopitaluga/patooverflow/blob/master/node-javascript.md#express-hello-world-starter)

------
Ignore the rest code. Is styling for local display of this file using https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
<style>
  .markdown-body {
    position: relative;
  }
  .cpy-btns {
    background: transparent;
    border: 0;
    cursor: pointer;
    display: block;
    font-family: monospace;
    font-size: 11px;
    margin-top: -4px;
    position: absolute;
    right: 45px;
    width: auto;
  }
  .cpy-btns::before {
    content: 'COPY'
  }
</style>
