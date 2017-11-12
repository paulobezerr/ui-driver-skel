# XenServer rancher machine driver UI

Rancher UI driver for XenServer docker-machine driver.

## Install

* Go to Admin -> Machine Drivers -> Add Machine Driver
  * Binary URL, see `https://github.com/xenserver/docker-machine-driver-xenserver/releases`
  * UI URL: see `https://github.com/paulobezerr/ui-driver-xenserver/releases`
  * Wait for the driver to become "Active"
  * Go to Infrastructure -> Hosts -> Add Host, your driver and custom UI should show up.

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

* Add a Machine Driver in Rancher (Admin tab -> Settings -> Machine Drivers)
  * Name: Your `xenserver`
  * Download URL: The URL for the driver binary (See `https://github.com/xenserver/docker-machine-driver-xenserver/releases`)
  * Custom UI URL: The URL you uploaded the `dist` folder to, e.g. `https://github.com/paulobezerr/ui-driver-xenserver/releases/download/v1.0.0/component.js`)
* Wait for the driver to become "Active"
* Go to Infrastructure -> Hosts -> Add Host, your driver and custom UI should show up.
