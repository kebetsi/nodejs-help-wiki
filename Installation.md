### How to install Node.js via binary archive on Linux?

1. Unzip the binary archive to any directory you wanna install Node, I use `/usr/local/lib/nodejs`

 ```
  VERSION=v8.11.4
  DISTRO=linux-x64
  sudo mkdir /usr/local/lib/nodejs
  sudo tar -xJvf node-$VERSION-$DISTRO.tar.xz -C /usr/local/lib/nodejs 
  sudo mv /usr/local/lib/nodejs/node-$VERSION-$DISTRO /usr/local/lib/nodejs/node-$VERSION
 ```

2. Set the environment variable `~/.profile`, add below to the end

 ```
 # Nodejs
 export NODEJS_HOME=/usr/local/lib/nodejs/node-$VERSION/bin
 export PATH=$NODEJS_HOME:$PATH
 ```
3. Refresh profile

```
. ~/.profile
```

4. Test installation using

 `$ node -v`
 
 `$ npm version`

 the normal output is:

 ```
 ➜  node -v
v8.11.4
➜  npm version
{ npm: '5.6.0',
  ares: '1.10.1-DEV',
  cldr: '31.0.1',
  http_parser: '2.7.0',
  icu: '59.1',
  modules: '57',
  nghttp2: '1.25.0',
  node: '8.11.4',
  openssl: '1.0.2n',
  tz: '2017b',
  unicode: '9.0',
  uv: '1.15.0',
  v8: '6.1.534.50',
  zlib: '1.2.11' }

 ```
### To create a **sudo** link:

```
sudo ln -s /usr/local/lib/nodejs/node-$VERSION/bin/node /usr/bin/node

sudo ln -s /usr/local/lib/nodejs/node-$VERSION/bin/npm /usr/bin/npm

sudo ln -s /usr/local/lib/nodejs/node-$VERSION/bin/npx /usr/bin/npx
````