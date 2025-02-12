# Mock Node
A configurable mock server with an intuitive configuration management interface and a http api.

[![Build Status](https://travis-ci.org/ianunay/mock-node.svg?branch=master)](https://travis-ci.org/ianunay/mock-node)


## Installing and Runing the server

### Standalone

  1. clone/download this repository
  2. make sure you have node and npm installed
  3. run <code>npm install</code> to download required packages
  4. <code>node server.js</code> to run the server

### npm global install

  1. npm install -g mocknode
  2. run <code>mocknode</code> to start the server

### npm local install

  1. npm install --save mocknode
  2. add an npm script entry in the package.json <code>"mocknode": "mocknode"</code>
  3. run <code>npm run mocknode</code> to start the server

and open [https://localhost:3000/mocknode/](https://localhost:3000/mocknode/) in your browser to configure mocknode

## A running instance on heroku

[https://mocknode.herokuapp.com/mocknode/](https://mocknode.herokuapp.com/mocknode/)
please go easy on this :)


## The port

The order of preference for the port on which mocknode runs is:

env variable of process > port option passed > 3000

<code>mocknode --port 4000</code> starts the server on port 4000, unless a PORT env variable exists for the process.


## Mocknode configuration

Open [https://localhost:3000/mocknode/](https://localhost:3000/mocknode/) in your browser to configure mocknode

![alt tag](https://cloud.githubusercontent.com/assets/1129363/14989097/237e4478-114e-11e6-8083-b56cfa95dc4f.png)

All your changes are saved in the config files - config.json, config-stub.json and the stubs folder, which ensure all your changes are saved if you restart mocknode.

## HTTP API

Mocknode exposes a series of endpoints which can help you integrate mocknode with your code - [ test scripts for example ]


| enpoint                         |  method  |     params      |
| :------------------------------ | --------:| :------------:  |
| /mocknode/api/config            |    GET   |        -        |
| /mocknode/api/stubconfig        |    GET   |        -        |
| /mocknode/api/getstub           |    GET   |      name       |
| /mocknode/api/modifyroute       |   POST   |   route config  |
| /mocknode/api/deleteroute       |    GET   |      route      |
| /mocknode/api/modifystub        |   POST   |    stub config  |
| /mocknode/api/deletestub        |    GET   |      name       |
| /mocknode/api/modifydynamicstub |   POST   |    stub config  |
| /mocknode/api/deletedynamicstub |    GET   |      name       |


mocknode interface uses the above endpoints to interact with the server, inspect the network of the browser to better understand the parameters used in each api.

### Troubleshooting

The config files and the stubs folder mentioned above have all the information regarding your configuration.

### License

MIT
