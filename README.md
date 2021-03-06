- - -

## My modified Bel node code installation instructions:
The modifications are nothing but this repository contains the installed node_modules. 'belrium-js' module which is a dependency of belriumnode is no longer available, so belriumnode cannot be installed. So this repo is my previously installed belriumnode code which already has 'belrium-js' installed. 
This clone also has KYC check mocked for DApps development purposes.

# Setup instructions:
```
sudo apt update
sudo apt install npm nodejs
sudo apt install sqlite3
mkdir logs
```

# That's it, to run the blockchain:
```
node app.js
```

This runs the blockchain in a localnet at port 9305. 

The other steps below belong to the original belriumnode code,
You don't need to follow any of those additional steps below.
I didn't want to remove the original README so I left it just like it is.

# Belrium

Belrium system is a decentralized application platform, which is designed to lower the threshold for developers, such as using JavaScript as develop language, supporting relational database to save transaction data, and making DAPP development be similar with traditional Web application. It is sure that these characteristics are very attractive to developers and SMEs. The ecosystem of the whole platform cannot be improved until developers make a huge progress on productivity. Also, Belrium platform is designed to be open for various fields, not limited to some particular parts such as finance, file storage, or copyright proof. It provides underlying and abstract API which can be combined freely to create different types of applications. In consensus mechanism, Belrium inherits and enhances DPOS algorithm, by which the possibility of forks and risk of duplicate payments would be significantly reduced. Furthermore, Belrium sidechain mode not only can mitigate the pressure of blockchain expansion, but also make DAPP more flexible and personal. Belrium system, as a proactive, low-cost and full stack solution, will surely be a next generation incubator of decentralized applications.


## System Dependency

- nodejs v6.2.0+
- npm 3.10+ (not cnpm)
- node-gyp v3.6.2+ (suggested)
- sqlite v3.8.2+
- g++
- libssl

## Installation for ubuntu 14.04.x or higher.

```
# Install dependency package
sudo apt-get install curl sqlite3 ntp wget git libssl-dev openssl make gcc g++ autoconf automake python build-essential -y
# libsodium for ubuntu 14.04
sudo apt-get install libtool -y
# libsodium for ubuntu 16.04
sudo apt-get install libtool libtool-bin -y

# Install nvm
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
# This loads nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# Install node and npm for current user.
nvm install v8
# check node version and it should be v8.x.x
node --version

# Install node packages
npm install
```

## Web Wallet

```
cd public/

npm install bower -g
npm install browserify -g
npm install gulp  -g

npm install
# angular chose "angular#~1.5.3 which resolved to 1.5.11 and is required by Belrium"
bower install

npm run build
gulp build-test #This make the front-end files in public dir.
```

## Installation on docker.

[Please install Docker firstly](https://store.docker.com/search?offering=community&type=edition)

```
# pull belrium code docker image
docker pull belriumplatform/belrium:v1.3.0
# run docker and belrium
docker run -i -t --name belrium1.3.0 -p 4096:4096 belriumplatform/belrium:v1.3.0 /bin/bash
root@e149b6732a48:/# cd /data/belrium && ./belrium start
Belrium server started as daemon ...
```

## Run

```
cd belrium && node app.js
or
cd belrium && ./belrium_manager.bash start
```
Then you can open ```http://localhost:9305``` in you browser.

## Usage

```
node app.js --help

  Usage: app [options]

  Options:

    -h, --help                 output usage information
    -V, --version              output the version number
    -c, --config <path>        Config file path
    -p, --port <port>          Listening port number
    -a, --address <ip>         Listening host name or ip
    -b, --blockchain <path>    Blockchain db path
    -g, --genesisblock <path>  Genesisblock path
    -x, --peers [peers...]     Peers list
    -l, --log <level>          Log level
    -d, --daemon               Run belrium node as daemon
    --reindex                  Reindex blockchain
    --base <dir>               Base directory
```

## Default localnet genesis account

```
// This is the genesis account of localnet and one hundred million XAS in it.
{
  "keypair": {
    "publicKey": "8065a105c785a08757727fded3a06f8f312e73ad40f1f3502e0232ea42e67efd",
    "privateKey": "a64af28537545301f66579604628b55c7a7a102752bbd8f0b0d152f9754e78d58065a105c785a08757727fded3a06f8f312e73ad40f1f3502e0232ea42e67efd"
  },
  "address": "14762548536863074694",
  "secret": "someone manual strong movie roof episode eight spatial brown soldier soup motor" // password
}
```
