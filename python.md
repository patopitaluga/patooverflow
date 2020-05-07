# Python Cheatsheet

Index:
* [Know which version is installed and ready in PATH](#know-which-version-is-installed-and-ready-in-path)
* [Stop the execution a py file](#stop-the-execution-of-a-py-file)

------

## <a name="know-which-version-is-installed-and-ready-in-path"></a> Know which version is installed and ready in PATH

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
python -V
```

------

## <a name="stop-the-execution-of-a-py-file"></a> Stop the execution a py file

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
sys.exit("Error message")
```
or

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
sys.exit(0)
```

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
