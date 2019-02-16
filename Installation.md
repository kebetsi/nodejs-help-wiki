
***
### How to install Node.js via binary archive on Linux?

1. Unzip the binary archive to any directory you wanna install Node, I use `/usr/local/lib/nodejs`

 ```
  VERSION=v10.15.0
  DISTRO=linux-x64
  sudo mkdir -p /usr/local/lib/nodejs
  sudo tar -xJvf node-$VERSION-$DISTRO.tar.xz -C /usr/local/lib/nodejs 
 ```

2. Set the environment variable `~/.profile`, add below to the end

 ```
 # Nodejs
 VERSION=v10.15.0
 DISTRO=linux-x64
 export PATH=/usr/local/lib/nodejs/node-$VERSION-$DISTRO/bin:$PATH
 ```
3. Refresh profile

```
. ~/.profile
```

4. Test installation using

 `$ node -v`
 
 `$ npm version`
  
 `$ npx -v`

 the normal output is:

 ```
 ➜  node -v
v10.15.1
➜  npm version
{ npm: '6.4.1',
  ares: '1.15.0',
  cldr: '33.1',
  http_parser: '2.8.0',
  icu: '62.1',
  modules: '64',
  napi: '3',
  nghttp2: '1.34.0',
  node: '10.15.1',
  openssl: '1.1.0j',
  tz: '2018e',
  unicode: '11.0',
  uv: '1.23.2',
  v8: '6.8.275.32-node.12',
  zlib: '1.2.11' }

 ```
### To create a **sudo** link:

```
sudo ln -s /usr/local/lib/nodejs/node-$VERSION-$DISTRO/bin/node /usr/bin/node

sudo ln -s /usr/local/lib/nodejs/node-$VERSION-$DISTRO/bin/npm /usr/bin/npm

sudo ln -s /usr/local/lib/nodejs/node-$VERSION-$DISTRO/bin/npx /usr/bin/npx
```