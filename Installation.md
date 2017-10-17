### How to install Node.js via binary archive on Linux?

1. Unzip the binary archive to any directory you wanna install Node, I use `/usr/lib/nodejs`

 ```
  sudo mkdir /usr/lib/nodejs
  sudo tar -xJvf node-v6.5.0-linux-x64.tar.xz -C /usr/lib/nodejs 
  sudo mv /usr/lib/nodejs/node-v6.5.0-linux-x64 /usr/lib/nodejs/node-v6.5.0
 ```

2. Set the environment variable `~/.profile`, add below to the end

 ```
 # Nodejs
 export NODEJS_HOME=/usr/lib/nodejs/node-v6.5.0
 export PATH=$NODEJS_HOME/bin:$PATH
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
 ➜  nodejs node -v
v6.5.0
➜  npm version
{ npm: '3.10.3',
  ares: '1.10.1-DEV',
  http_parser: '2.7.0',
  icu: '57.1',
  modules: '48',
  node: '6.5.0',
  openssl: '1.0.2h',
  uv: '1.9.1',
  v8: '5.1.281.81',
  zlib: '1.2.8' }

 ```