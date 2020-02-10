AnywherePlus 随启随用的可上传静态文件服务器
==============================

Running static file server anywherePlus. 随时随地将你的当前目录变成一个静态文件服务器的根目录。

## Installation

Install it as a command line tool via `npm -g`.

```sh
npm install anywherePlus-plus -g
```

## Execution

```sh
$ anywherePlus
// or with port
$ anywherePlus -p 8000
// or start it but silent(don't open browser)
$ anywherePlus -s
// or with hostname
$ anywherePlus -h localhost -p 8888
// or with folder
$ anywherePlus -d ~/git/anywherePlus
// or enable html5 history
$ anywherePlus -f /index.html
```

## Help

```sh
$ anywherePlus --help
Usage:
  anywherePlus --help // print help information
  anywherePlus // 8000 as default port, current folder as root
  anywherePlus 8888 // 8888 as port
  anywherePlus -p 8989 // 8989 as port
  anywherePlus -s // don't open browser
  anywherePlus -h localhost // localhost as hostname
  anywherePlus -d /home // /home as root
  anywherePlus -f /index.html  // Enable html5 history,the index is /index.html
  anywherePlus --proxy http://localhost:7000/api // Support shorthand URL, webpack.config.js or customize config file
```

#### Proxy argvs

**Shorthand URL**
```
anywherePlus --proxy http://localhost:7000/api
                 \___________________/\___/
                              |         |
                           target    context
```
More about the [shorthand configuration](https://github.com/chimurai/http-proxy-middleware#shorthand).

**Webpack conofig**
```javascript
// webpack.conofig.js
module.exports = {
  devServer: {
    proxy: {
      '/api': {
        target: 'http://localhost:7000',
        changeOrigin: true
      }
    }
  }
}
```

**Customize config**
```javascript
// proxy.config.js
module.exports = {
  '/api': {
    target: 'http://localhost:7000',
    changeOrigin: true
  }
}
```
More proxy [http-proxy-middleware](https://github.com/chimurai/http-proxy-middleware#context-matching) help.

## Visit

```
http://localhost:8000
```
Automatically open default browser. 执行命令后，默认浏览器将为您自动打开主页。

## License
The MIT license.
