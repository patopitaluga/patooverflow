# CSS Cheatsheet and useful snippets

On github: https://github.com/patopitaluga/patooverflow/blob/master/css.md

Also useful:
* [Console / terminal cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/console-terminal.md)
* [Node / Javascript cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/node-javascript.md)

Index:
* [Change input placeholder color](#change-input-placeholder-color)

Useful tools:
copy code Chrome extension: https://chrome.google.com/webstore/detail/copy-code/ophfcfplhjmiakmfeemkpaoofhjlmkof

------
## <a name="change-input-placeholder-color"></a> Change input placeholder color

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
::-webkit-input-placeholder { /* WebKit, Blink, Edge */
  color: #909;
}
:-moz-placeholder { /* Mozilla Firefox 4 to 18 */
  color: #909;
  opacity: 1;
}
::-moz-placeholder { /* Mozilla Firefox 19+ */
  color: #909;
  opacity: 1;
}
:-ms-input-placeholder { /* Internet Explorer 10-11 */
  color: #909;
}
::-ms-input-placeholder { /* Microsoft Edge */
  color: #909;
}

::placeholder { /* Most modern browsers support this now. */
  color: #909;
}
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
