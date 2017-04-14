# Browsertime extension
Extension for Firefox and Chrome that is used in [Browsertime](https://github.com/sitespeedio/browsertime) to:
* Set request headers
* Block requests

and more things in the future.

## Set request headers
Set request headers:
* Key secret with value 87sghwgaf&&ga9ja:
* Key user with value hoppla

Go to http://127.0.0.1/?rh=secret:87sghwgaf&&ga9ja:&rh=user:hoppla

Set for a specific domain:
Go to http://127.0.0.1/?rh=secret:87sghwgaf&&ga9ja:&rh=user:hoppla&domain=www.sitespeed.io


## Block requests
Block all requests on w.cdn-expressen.se

Go to http://http://127.0.0.1/?bl=w.cdn-expressen.se

Block all requests on w.cdn-expressen.se and www.cdn-expressen.se

Go to http://http://127.0.0.1/?bl=w.cdn-expressen.se&bl=www.cdn-expressen.se

# Test the plugin in Firefox

Install web-ext:
<pre>$ npm install --global web-ext
</pre>

And then run <pre>$ web-ext run --browser-console
</pre>

Setup your own server on localhost (server.js):
<pre>
const http = require('http');
const fs = require('fs');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Browsertime internal server');
 }).listen(8081);
</pre>

then <code>node server.js</code> and access 127.0.0.1:8081.

# Test in Chrome

Follow instruction on [https://support.google.com/chrome_webstore/answer/2664769?hl=en](https://support.google.com/chrome_webstore/answer/2664769?hl=en). Remember that you need to reload the plugin when you change things.

# Test in Browsertime

For Chrome, build the extension by click on the button "Pack extension" and the copy the file to <i>browsertime/vendor/browsertime-extension.crx</i>.

For Firefox use web-ext sign ... but the current version doesn't support webextension based on a manifest.json. 