# Nginx Cheatsheet

Index:
* [Find nginx.conf file path](#find-nginxconf-file-path)
* [Setup nginx.conf file to proxy a url to localhost](#setup-nginxconf-file-to-proxy-a-url-to-localhost)

------

## <a name="find-nginxconf-file-path"></a> Find nginx.conf file path
```
nginx -t
```

------
## <a name="setup-nginxconf-file-to-proxy-a-url-to-localhost"></a> Setup nginx.conf file to proxy a url to localhost

Example for port 3000

```
http {
    server_names_hash_bucket_size 128;
    include       mime.types;
    default_type  application/octet-stream;

    sendfile        on;
    keepalive_timeout  65;

...

    server {
        listen 80;
        server_name  theurlyouwanttorunlocal.com;
        location / {
            proxy_pass http://localhost:3000;
        }
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
