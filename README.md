## reproduce

### 1. run dev server

```
cd moduleLoadFailed
npm install
npm run dev
```

you can access `http://localhost:3000`, everything works well.

### 2. reverse proxy

```
brew install nginx
cp ./gateway.conf /usr/local/etc/nginx/servers
nginx -s reload
```

try to access `http://localhost` on broswer and it will reproduce.

on chrome:

```
GET http://localhost/node_modules/.vite/element-plus_es.js?v=c48a10d4 net::ERR_INCOMPLETE_CHUNKED_ENCODING 200 (OK)
```

on firefox:

```
Loading failed for the module with source “http://localhost/node_modules/.vite/element-plus_es.js?v=c48a10d4”.
```
