# XenServer rancher machine driver UI

Rancher UI driver for XenServer docker-machine driver.

## Install

* Put the URL in whitelist:
  * Admin -> Settings -> Advanced settings
  * Append in ``api.proxy.whitelist`` the github URL: ``paulobezerr.github.io``
* Go to Admin -> Machine Drivers -> Add Machine Driver
  * Binary URL, get in `https://github.com/xenserver/docker-machine-driver-xenserver/releases`
  * UI URL: `https://paulobezerr.github.io/ui-driver-xenserver/dist/component.js`
  * Wait for the driver to become "Active"
  * Go to Infrastructure -> Hosts -> Add Host, and select the XenServer

## Development

This package contains a small web-server that will serve up the custom driver UI at `http://localhost:3000/component.js`.  You can run this while developing and point the Rancher settings there.
* `npm install`
* `bower install`
* `npm start`
* The compiled files are viewable at http://localhost:3000.
* **Note:** The development server does not currently automatically restart when files are changed.

## Building

* `npm build`
* Copy the contents of the `dist` directory onto a webserver.
  * If your Rancher is configured to use HA or SSL, the server must also be available via HTTPS.

## Using

* Put the URL in whitelist:
  * Admin -> Settings -> Advanced settings
  * Append in ``api.proxy.whitelist`` the github URL: ``paulobezerr.github.io``
* Install (Admin tab -> Settings -> Machine Drivers)
  * Name: Your `xenserver`
  * Download URL: The URL for the driver binary (See `https://github.com/xenserver/docker-machine-driver-xenserver/releases`)
  * Custom UI URL: `https://paulobezerr.github.io/ui-driver-xenserver/dist/component.js`)
* Wait for the driver to become "Active"
* Go to Infrastructure -> Hosts -> Add Host
  * The Xen Server will be there for you!

## Help wanted

The advanced options must be modified.  
There are some options does not apply, for example ``Docker Install URL``.  
I don't know how to do this yet, but help it's very welcome!
Thank you for use!
