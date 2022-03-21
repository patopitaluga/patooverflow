# Docker Cheatsheet

Index:
* [List Docker Containers](#list-docker-containers)
* [Stop Docker Container](#stop-docker-container)
* [Enter a Docker Container run commands](#enter-a-docker-container)

------

## <a name="list-docker-containers"></a> List Docker Containers

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
docker container ls
```

------

## <a name="stop-docker-container"></a> Stop Docker Container

```
docker stop my_container
```

------

## <a name="enter-a-docker-container"></a> Enter a Docker Container run commands

```
docker exec -it container-name
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
