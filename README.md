pome-masterha-plugin
======================

master ha plugin for pome, it can be used in pome(>=0.6).

pome-masterha-plugin is a master ha plugin for pome, which uses zookeeper to make master as high availability cluster.

##Installation

```
npm install pome-masterha-plugin
```

##Usage

Make sure you have installed zookeeper first, then you have built the path you pass to pome. The configure code in app.js is as follows:

```
var masterhaPlugin = require('pome-masterha-plugin');

app.configure('production|development', function() {
  
  app.use(masterhaPlugin, {
    zookeeper: {
      server: '127.0.0.1:2181',
      path: '/pome/master'
    }
  });

});

```

You can start your application using pome start as before, then use [pome-daemon](https://github.com/pomejs/pome-daemon) to start a slave master.
