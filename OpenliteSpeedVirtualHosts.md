Node.js Apps with OpenLiteSpeed

Node.js is a platform that generally runs as a separate web server. OpenLiteSpeed Web Server can be configured to proxy traffic to Node.js so that users can run Node.js applications (like Ghost) on their sites.

This wiki will go over how to run Node.js apps with OpenLiteSpeed. It assumes that you already have a working version of Node.js installed and virtual hosts set up to run it on.

Requirements
OpenLiteSpeed version 1.4.41+
Setup
Install Nodejs
If you haven’t already, please install the nodejs application:
CentOS

```
yum install nodejs
```

```
apt-get install nodejs
```

Set up Context

This example assumes you are using the default document root + URI: /node/

Navigate to Web Admin > Virtual Hosts > Context > Add

Type = App Server

URI = /node/

Location = /usr/local/lsws/Example/node/

Binary Path = /usr/bin/node

Application Type = node

Verification

Create a node directory under your document root.

Create a app.js file with the following content:

```
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World form node js app.js\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

Visit http://Server_IP:Port/node/ in your browser and you should see:

Hello World form node js app.js 

Optional Settings

Custom Binary Path

If you want to change the node path, just update the Context and set Binary Path = /usr/node.
