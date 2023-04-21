# Postgres Cheatsheet

Index:
* [Run postgres cli from terminal](#run-postgres-cli-from-terminal)
* [Quit postgres cli](#quit-postgres-cli)
* [List tables](#list-tables)
* [Drop database from terminal](#drop-db-from-terminal)

------

## <a name="run-postgres-cli-from-terminal"></a> Run postgres cli from terminal

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
psql
```

------

## <a name="quit-postgres-cli"></a> Quit postgres cli

```
\q
```

------

## <a name="list-tables"></a> List tables

```
\dt
```

------

## <a name="list-tables"></a> Output to txt file

```
\o /Users/patopitaluga/output.txt
select * from users;
\o
```

------

## <a name="drop-db-from-terminal"></a> Drop database from terminal

```
dropdb 'database name'
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
