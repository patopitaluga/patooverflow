# MySQL Cheatsheet and useful snippets

On github: https://github.com/patopitaluga/patooverflow/blob/master/mysql.md

Also useful:
* [Console / terminal cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/console-terminal.md)
* [Node / Javascript cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/node-javascript.md)
* [PHP cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/php.md)

Index:
* [Fix cannot truncate a table referenced in a foreign key constraint](#cannot-truncate-a-table-referenced-in-a-foreign-key-constraint)

Useful tools:
copy code Chrome extension: https://chrome.google.com/webstore/detail/copy-code/ophfcfplhjmiakmfeemkpaoofhjlmkof

------
## <a name="cannot-truncate-a-table-referenced-in-a-foreign-key-constraint"></a> Fix cannot truncate a table referenced in a foreign key constraint

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>

Before the truncate
```
SET FOREIGN_KEY_CHECKS = 0;
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
