# Node Serialport

<!-- STOP! WAIT! BEFORE YOU EDIT!

README.md is a generated file don't edit it!

This file is generated from .docs/README.hbs and the JavaScript files themselves.
See our contributing guide for more information.

https://github.com/EmergingTechnologyAdvisors/node-serialport/blob/master/CONTRIBUTING.md#writing-docs

-->

[![npm](https://img.shields.io/npm/dm/serialport.svg?maxAge=2592000)](http://npmjs.com/package/serialport)
[![Gitter chat](https://badges.gitter.im/EmergingTechnologyAdvisors/node-serialport.svg)](https://gitter.im/EmergingTechnologyAdvisors/node-serialport)
[![Dependency Status](https://david-dm.org/EmergingTechnologyAdvisors/node-serialport.svg)](https://david-dm.org/EmergingTechnologyAdvisors/node-serialport)
[![Dependency Status](https://dependencyci.com/github/EmergingTechnologyAdvisors/node-serialport/badge)](https://dependencyci.com/github/EmergingTechnologyAdvisors/node-serialport)
[![Coverage Status](https://coveralls.io/repos/github/EmergingTechnologyAdvisors/node-serialport/badge.svg?branch=master)](https://coveralls.io/github/EmergingTechnologyAdvisors/node-serialport?branch=master)
[![Build Status](https://travis-ci.org/EmergingTechnologyAdvisors/node-serialport.svg?branch=master)](https://travis-ci.org/EmergingTechnologyAdvisors/node-serialport)
[![Build status](https://ci.appveyor.com/api/projects/status/u6xe3iao2crd7akn/branch/master?svg=true)](https://ci.appveyor.com/project/j5js/node-serialport/branch/master)

For support you can open a [github issue](https://github.com/EmergingTechnologyAdvisors/node-serialport/issues/new), for discussions, designs, and clarifications, we recommend you join our [Gitter Chat room](https://gitter.im/EmergingTechnologyAdvisors/node-serialport). We have two related projects [Browser Serialport](https://github.com/garrows/browser-serialport) "just like Node Serialport but for browser apps", and [Serialport Test Piliot](https://github.com/j5js/serialport-test-pilot) which helps us test serialport.

If you'd like to contribute please take a look at [contribution guide](CONTRIBUTING.md) and [code of conduct](CODE_OF_CONDUCT.md). You also might want to see the [road map](https://github.com/EmergingTechnologyAdvisors/node-serialport/issues/746). We also have issues tagged ["good first PR"](https://github.com/EmergingTechnologyAdvisors/node-serialport/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+pr%22) if you'd like to start somewhere specific. We'll do our best to support you until your PR is merged.

***

# Which version of Serialport would you like documentation for?

You're reading the README for the master branch of serialport. You probably want to be looking at the README of our latest release. See our [change log](changelog.md) for what's new and our [upgrade guide](UPGRADE_GUIDE.md) for a walk through on what to look out for between major versions.

- [`serialport@5.0.0-beta2` docs are here](https://github.com/EmergingTechnologyAdvisors/node-serialport/blob/5.0.0-beta2/README.md) this is the latest `5.x` releases.
- [`serialport@4.0.3` docs are here](https://github.com/EmergingTechnologyAdvisors/node-serialport/blob/4.0.3/README.md) it is the latest `4.x` releases.
- [`serialport@3.1.2` docs are here](https://github.com/EmergingTechnologyAdvisors/node-serialport/blob/3.1.2/README.md) it is the latest `3.x` releases.
- [`serialport@2.1.2` docs are here](https://github.com/EmergingTechnologyAdvisors/node-serialport/blob/2.1.2/README.md) it was the last `2.x` release
- [`serialport@1.7.4` docs are here](https://github.com/EmergingTechnologyAdvisors/node-serialport/blob/v1.7.4/README.md) it was the last `1.x` release

***

Imagine a world where you can write JavaScript to control blenders, lights, security systems, or even robots. Yes, I said robots. That world is here and now with node serialport. It provides a very simple interface to the low level serial port code necessary to program [Arduino](http://www.arduino.cc/) chipsets, [X10](http://www.smarthome.com/manuals/protocol.txt) wireless communications, or even the rising [Z-Wave](http://www.z-wave.com/modules/ZwaveStart/) and [Zigbee](http://www.zigbee.org/) standards. The physical world is your oyster with this goodie. For a full break down of why we made this, please read [NodeBots - The Rise of JS Robotics](http://www.voodootikigod.com/nodebots-the-rise-of-js-robotics).

***

For getting started with node-serialport, we recommend you begin with the following articles:
* [Johnny-Five](http://johnny-five.io/#hello-world) - The Johnny-Five Robotics and IoT platform's 6 line "Hello World" (awesome).
* [Arduino Node Security Sensor Hacking](http://nexxylove.tumblr.com/post/20159263403/arduino-node-security-sensor-hacking) - A great all around "how do I use this" article.
* [NodeBots - The Rise of JS Robotics](http://www.voodootikigod.com/nodebots-the-rise-of-js-robotics) - A survey article of why one would want to program robots in JS and how this all started.

***
* [Platform Support](#platform-support)
* [Installation](#installation-instructions)
* [Installation Special Cases](#installation-special-cases)
  * [Windows](#windows)
  * [Mac OS X](#mac-os-x)
  * [Ubuntu/Debian Linux](#ubuntudebian-linux)
  * [Alpine Linux](#alpine-linux)
  * [Raspberry Pi Linux](#raspberry-pi-linux)
  * [Illegal Instruction](#illegal-instruction)
  * [Electron](#electron)

* [License](#license)
* [Usage](#usage)
  * [Opening a Port](#opening-a-port)
* [SerialPort](#exp_module_serialport--SerialPort) ⏏
    * [`new SerialPort(path, [options], [openCallback])`](#new_module_serialport--SerialPort_new)
    * _instance_
        * [`.open([callback])`](#module_serialport--SerialPort+open)
        * [`.update([options], [callback])`](#module_serialport--SerialPort+update)
        * [`.write(data, [encoding], [callback])`](#module_serialport--SerialPort+write) ⇒ <code>boolean</code>
        * [`.read([size])`](#module_serialport--SerialPort+read) ⇒ <code>string</code> &#124; <code>Buffer</code> &#124; <code>null</code>
        * [`.close(callback)`](#module_serialport--SerialPort+close)
        * [`.set([options], [callback])`](#module_serialport--SerialPort+set)
        * [`.get([callback])`](#module_serialport--SerialPort+get)
        * [`.flush([callback])`](#module_serialport--SerialPort+flush)
        * [`.drain([callback])`](#module_serialport--SerialPort+drain)
        * [`.pause()`](#module_serialport--SerialPort+pause) ⇒
        * [`.resume()`](#module_serialport--SerialPort+resume) ⇒
        * [`Event: "error"`](#module_serialport--SerialPort+event_error)
        * [`Event: "open"`](#module_serialport--SerialPort+event_open)
        * [`Event: "data"`](#module_serialport--SerialPort+event_data)
        * [`Event: "disconnect"`](#module_serialport--SerialPort+event_disconnect)
        * [`Event: "close"`](#module_serialport--SerialPort+event_close)
    * _static_
        * [`.Binding`](#module_serialport--SerialPort.Binding) : <code>[Binding](#module_serialport--SerialPort..Binding)</code>
        * [`.parsers`](#module_serialport--SerialPort.parsers) : <code>object</code>
        * [`.list(callback)`](#module_serialport--SerialPort.list) : <code>function</code>
    * _inner_
        * [~Binding](#module_serialport--SerialPort..Binding) : <code>Class</code>
            * [`new Binding(options)`](#new_module_serialport--SerialPort..Binding_new)
            * [`.list(callback)`](#module_serialport--SerialPort..Binding+list)
            * [`.open(path, openOptions, openCallback)`](#module_serialport--SerialPort..Binding+open)
            * [`.close(callback)`](#module_serialport--SerialPort..Binding+close)
            * [`.read(data, length, readCallback)`](#module_serialport--SerialPort..Binding+read)
            * [`.write(data, writeCallback)`](#module_serialport--SerialPort..Binding+write)
            * [`.set([options], callback)`](#module_serialport--SerialPort..Binding+set)
            * [`.get([callback])`](#module_serialport--SerialPort..Binding+get)
            * [`.flush(callback)`](#module_serialport--SerialPort..Binding+flush)
            * [`.drain(callback)`](#module_serialport--SerialPort..Binding+drain)
        * [`~readCallback`](#module_serialport--SerialPort..readCallback) : <code>function</code>
        * [`~errorCallback`](#module_serialport--SerialPort..errorCallback) : <code>function</code>
        * [`~modemBitsCallback`](#module_serialport--SerialPort..modemBitsCallback) : <code>function</code>
        * [`~openOptions`](#module_serialport--SerialPort..openOptions) : <code>Object</code>
        * [`~listCallback`](#module_serialport--SerialPort..listCallback) : <code>function</code>
* [Command Line Tools](#command-line-tools)
  * [Serial Port List](#serial-port-list)
  * [Serial Port Terminal](#serial-port-terminal)

***

## Platform Support
`serialport` supports and tests against the following platforms, architectures and node versions.

| Platform / Arch | Node v0.10.x | Node v0.12.x | Node v4.x | Node v6.x |
|       ---       | --- | --- | --- | --- |
| Linux / ia32    |  ☑  |  ☑  |  ☑  |  ☑  |
| Linux / x64     |  ☑  |  ☑  |  ☑  |  ☑  |
| Linux / ARM v6¹ |  ☐  |  ☐  |  ☐  |  ☐  |
| Linux / ARM v7¹ |  ☐  |  ☐  |  ☐  |  ☐  |
| Linux / ARM v8¹ |  ☐  |  ☐  |  ☐  |  ☐  |
| Linux / MIPSel¹ |  ☐  |  ☐  |  ☐  |  ☐  |
| Linux / PPC64¹  |  ☐  |  ☐  |  ☐  |  ☐  |
| Windows² / x86  |  ☑  |  ☑  |  ☑  |  ☑  |
| Windows² / x64  |  ☑  |  ☑  |  ☑  |  ☑  |
| OSX³ / x64      |  ☑  |  ☑  |  ☑  |  ☑  |

¹ ARM, MIPSel and PPC64¹ platforms are known to work but are not currently part of our test or build matrix. [#846](https://github.com/EmergingTechnologyAdvisors/node-serialport/issues/846) ARM v4 and v5 was dropped from NodeJS after Node v0.10.

² Windows 7, 8, 10, and 10 IoT are supported but only Windows Server 2012 R2 is tested by our CI.

³ OSX 10.4 Tiger and above are supported but only 10.9.5 Mavericks with Xcode 6.1 is tested in our CI.

## Installation Instructions

For most "standard" use cases (node v4.x on mac, linux, windows on a x86 or x64 processor), node-serialport will install nice and easy with a simple

```
npm install serialport
```

### Installation Special Cases

We are using [node-pre-gyp](https://github.com/mapbox/node-pre-gyp) to compile and post binaries of the library for most common use cases (linux, mac, windows on standard processor platforms). If you are on a special case, node-serialport will work, but it will compile the binary when you install.

This assumes you have everything on your system necessary to compile ANY native module for Node.js. This may not be the case, though, so please ensure the following are true for your system before filing an issue about "Does not install". For all operatings systems, please ensure you have Python 2.x installed AND not 3.0, node-gyp (what we use to compile) requires Python 2.x.

#### Windows

 * Windows 7, Windows 8.1, and Windows 10 are supported.
 * Might just download and install with no extra steps. If the downloaded binary fails you'll have to build it with the following steps.
 * Install [Visual Studio Express 2013 for Windows Desktop](http://www.microsoft.com/visualstudio/eng/2013-downloads#d-2013-express).
 * If you are hacking on an Arduino, be sure to install [the drivers](http://arduino.cc/en/Guide/windows#toc4).
 * Install [node.js](http://nodejs.org/) matching the bitness (32 or 64) of your operating system.
 * Install [Python 2.7.6](http://www.python.org/download/releases/2.7.6/) matching the bitness of your operating system.  For any questions, please refer to their [FAQ](http://docs.python.org/2/faq/windows.html). Default settings are perfect.
 * Open the 'Visual Studio Command Prompt' and add Python to the path.

#### Mac OS X

Ensure that you have at a minimum the xCode Command Line Tools installed appropriate for your system configuration. If you recently upgraded the OS, it probably removed your installation of Command Line Tools, please verify before submitting a ticket. To compile `node-serialport` with Node.js 4.x+, you will need to use g++ v4.8 or higher.

#### Ubuntu/Debian Linux

The best way to install any version of NodeJS is to use the [NodeSource Node.js Binary Distributions](https://github.com/nodesource/distributions#installation-instructions). Older versions of Ubuntu install nodejs with the wrong version and binary name. If you node binary is `nodejs` not `node` or if your node version is [`v0.10.29`](https://github.com/fivdi/onoff/wiki/Node.js-v0.10.29-and-native-addons-on-the-Raspberry-Pi) then you should follow these instructions.

The package `build-essential` is necessary to compile `serialport`. If there's a binary for your platform you won't need it. Keep rocking!


```
# Using Ubuntu and node 6
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs

# Using Debian and node 6, as root
curl -sL https://deb.nodesource.com/setup_6.x | bash -
apt-get install -y nodejs
```

#### Alpine Linux

[Alpine](http://www.alpinelinux.org/) is a (very) small distro, but it uses the musl standard library instead of glibc (that most other Linux distros use), so it requires compilation.

```
# If you don't have node/npm already, add that first
sudo apk add --no-cache nodejs

# Add the necessary build and runtime dependencies
sudo apk add --no-cache make gcc g++ python linux-headers udev

# Then we can install serialport, forcing it to compile
npm install serialport --build-from-source=serialport
```

#### Raspberry Pi Linux

Follow the instructions for [setting up a Raspberry pi for use with Johnny-Five and Raspi IO](https://github.com/nebrius/raspi-io/wiki/Getting-a-Raspberry-Pi-ready-for-NodeBots). These projects use Node Serialport under the hood.

| Revision       |      CPU              | Arm Version |
|   ----         |      ---              |     ---     |
| A, A+, B, B+   | 32-bit ARM1176JZF-S   |    ARMv6    |
| Compute Module | 32-bit ARM1176JZF-S   |    ARMv6    |
| Zero           | 32-bit ARM1176JZF-S   |    ARMv6    |
| B2             | 32-bit ARM Cortex-A7  |    ARMv7    |
| B3             | 32-bit ARM Cortex-A53 |    ARMv8    |


#### Illegal Instruction

The pre-compiled binaries assume a fully capable chip. The Galileo 2 for example lacks a few instruction sets from the `ia32` architecture. A few other platforms have similar issues. So if you get `Illegal Instruction` when trying to run serialport you'll need to rebuild the serialport binary by asking npm to rebuild it.

```bash
# Will ask npm to build serialport during install time
npm install serialport --build-from-source

# If you have a package that depends on serialport you can ask npm to rebuild it specifically.
npm rebuild serialport --build-from-source

# Or leave out the package name to rebuild everything.
npm rebuild --build-from-source
```

#### Electron

Electron is a framework for creating cross-platform desktop applications. Electron comes with it's own version of the Node.js runtime.

If you require `serialport` as a dependency for an Electron project you need to compile it for the version of Electron you're using in your project.

When you first install `serialport` it will compile against the version of Node.js on your machine, not against the Node.js runtime bundled with Electron.

To recompile `serialport` (or any native Node.js module) for Electron you can use `electron-rebuild`.

1. `npm install --save-dev electron-rebuild`
2. Delete existing Node.js binding `node_modules/serialport/build/Release/serialport.node`
3. Run `electron-rebuild`
  1. For Windows `.\node_modules\.bin\electron-rebuild.cmd`
  2. For Linux and macOS `./node_modules/.bin/electron-rebuild`

For more information on `electron-rebuild` visit the official [README](https://github.com/electron/electron-rebuild/blob/master/README.md).

## License
SerialPort is MIT licensed and all it's dependencies are MIT or BSD licensed.

## Usage

Opening a serial port:

```js
var SerialPort = require("serialport");
var port = new SerialPort("/dev/tty-usbserial1", {
  baudRate: 57600
});
```

When opening a serial port, you can specify (in this order).

1. Path to Serial Port - required.
1. Options - optional and described below.

### Opening a Port

Constructing a `SerialPort` object will open a port on `nextTick`. You can bind events while the port is opening but you must wait until it is open to `write()` to it. (Most port functions require an open port.) You can call code when a port is opened in three ways.

- The `open` event is always emitted when the port is opened
- The constructor's openCallback is passed to `.open()` when the `autoOpen` option hasn't been disabled, if you have disabled it the callback is ignored.
- The `.open()` function takes a callback that is called after the port is opened. This can be used if you disabled the `autoOpen` option or have previously closed an open port.


```js
var SerialPort = require('serialport');
var port = new SerialPort('/dev/tty-usbserial1');

port.on('open', function() {
  port.write('main screen turn on', function(err) {
    if (err) {
      return console.log('Error on write: ', err.message);
    }
    console.log('message written');
  });
});

// open errors will be emitted as an error event
port.on('error', function(err) {
  console.log('Error: ', err.message);
})
```

This could be moved to the constructor's callback.
```js
var SerialPort = require('serialport');
var port = new SerialPort('/dev/tty-usbserial1', function (err) {
  if (err) {
    return console.log('Error: ', err.message);
  }
  port.write('main screen turn on', function(err) {
    if (err) {
      return console.log('Error on write: ', err.message);
    }
    console.log('message written');
  });
});
```

When disabling the `autoOpen` option you'll need to open the port on your own.

```js
var SerialPort = require('serialport');
var port = new SerialPort('/dev/tty-usbserial1', { autoOpen: false });

port.open(function (err) {
  if (err) {
    return console.log('Error opening port: ', err.message);
  }

  // write errors will be emitted on the port since there is no callback to write
  port.write('main screen turn on');
});

// the open event will always be emitted
port.on('open', function() {
  // open logic
});
```

You can get updates of new data from the Serial Port as follows:

```js
port.on('data', function (data) {
  console.log('Data: ' + data);
});
```

You can write to the serial port by sending a string or buffer to the write method as follows:

```js
port.write('Hi Mom!');
port.write(new Buffer('Hi Mom!'));
```

Enjoy and do cool things with this code.

<a name="new_module_serialport--SerialPort_new"></a>

### `new SerialPort(path, [options], [openCallback])`
Create a new serial port object for the `path`. In the case of invalid arguments or invalid options when constructing a new SerialPort it will throw an error. The port will open automatically by default which is the equivalent of calling `port.open(openCallback)` in the next tick. This can be disabled by setting the option `autoOpen` to false.

**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| path | <code>string</code> | The system path of the serial port to open. For example, `/dev/tty.XXX` on Mac/Linux or `COM1` on Windows. |
| [options] | <code>[openOptions](#module_serialport--SerialPort..openOptions)</code> | Port configuration options |
| [openCallback] | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called when a connection has been opened. If this is not provided and an error occurs, it will be emitted on the ports `error` event. The callback will NOT be called if autoOpen is set to false in the openOptions as the open will not be performed. |


-

<a name="module_serialport--SerialPort+open"></a>

### `serialPort.open([callback])`
Opens a connection to the given serial port.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Emits**: <code>[open](#module_serialport--SerialPort+event_open)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [callback] | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called when a connection has been opened. If this is not provided and an error occurs, it will be emitted on the ports `error` event. |


-

<a name="module_serialport--SerialPort+update"></a>

### `serialPort.update([options], [callback])`
Changes the baud rate for an open port. Throws if you provide a bad argument. Emits an error or calls the callback if the baud rate isn't supported.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>object</code> | Only `baudRate` is currently supported |
| [options.baudRate] | <code>number</code> | The baud rate of the port to be opened. This should match one of commonly available baud rates, such as 110, 300, 1200, 2400, 4800, 9600, 14400, 19200, 38400, 57600, 115200. There is no guarantee, that the device connected to the serial port will support the requested baud rate, even if the port itself supports that baud rate. |
| [callback] | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called once the port's baud rate has been changed. If `.update` is called without an callback and there is an error, an error event will be emitted. |


-

<a name="module_serialport--SerialPort+write"></a>

### `serialPort.write(data, [encoding], [callback])` ⇒ <code>boolean</code>
Writes data to the given serial port. Buffers written data if the port is not open.

The write operation is non-blocking. When it returns, data may still have not actually been written to the serial port. See `drain()`.

Some devices like the Arduino reset when you open a connection to them. In these cases if you immediately write to the device they wont be ready to receive the data. This is often worked around by having the Arduino send a "ready" byte that your node program waits for before writing. You can also often get away with waiting around 400ms.

Even though serialport is a stream, when writing it can accept arrays of bytes in addition to strings and buffers. This extra functionality is pretty sweet.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Returns**: <code>boolean</code> - `false` if the stream wishes for the calling code to wait for the `'drain'` event to be emitted before continuing to write additional data; otherwise `true`.  

| Param | Type | Description |
| --- | --- | --- |
| data | <code>string</code> &#124; <code>array</code> &#124; <code>buffer</code> | Accepts a [`Buffer` ](http://nodejs.org/api/buffer.html) object, or a type that is accepted by the `Buffer` constructor (ex. an array of bytes or a string). |
| [encoding] | <code>string</code> | The encoding, if chunk is a String. Defaults to `'utf8'`. Also accepts `'ascii'`, `'base64'`, `'binary'`, `'hex'` See [Buffers and Character Encodings](https://nodejs.org/api/buffer.html#buffer_buffers_and_character_encodings) for all available options. |
| [callback] | <code>function</code> | Called once the write operation finishes. Data may not yet be flushed to the underlying port, no arguments. |


-

<a name="module_serialport--SerialPort+read"></a>

### `serialPort.read([size])` ⇒ <code>string</code> &#124; <code>Buffer</code> &#124; <code>null</code>
Request a number of bytes from the SerialPort. The `read()` method pulls some data out of the internal buffer and returns it. If no data available to be read, null is returned. By default, the data will be returned as a Buffer object unless an encoding has been specified using the `.setEncoding()` method.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Returns**: <code>string</code> &#124; <code>Buffer</code> &#124; <code>null</code> - The data from internal buffers  

| Param | Type | Description |
| --- | --- | --- |
| [size] | <code>number</code> | size specify how many bytes of data to return if available. |


-

<a name="module_serialport--SerialPort+close"></a>

### `serialPort.close(callback)`
Closes an open connection

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Emits**: <code>[close](#module_serialport--SerialPort+event_close)</code>  

| Param | Type | Description |
| --- | --- | --- |
| callback | <code>errorCallback</code> | Called once a connection is closed. |


-

<a name="module_serialport--SerialPort+set"></a>

### `serialPort.set([options], [callback])`
Set control flags on an open port. Uses [`SetCommMask`](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363257(v=vs.85).aspx) for windows and [`ioctl`](http://linux.die.net/man/4/tty_ioctl) for mac and linux.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [options] | <code>object</code> |  | All options are operating system default when the port is opened. Every flag is set on each call to the provided or default values. If options isn't provided default options will be used. |
| [options.brk] | <code>Boolean</code> | <code>false</code> |  |
| [options.cts] | <code>Boolean</code> | <code>false</code> |  |
| [options.dsr] | <code>Boolean</code> | <code>false</code> |  |
| [options.dtr] | <code>Boolean</code> | <code>true</code> |  |
| [options.rts] | <code>Boolean</code> | <code>true</code> |  |
| [callback] | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> |  | Called once the port's flags have been set. |


-

<a name="module_serialport--SerialPort+get"></a>

### `serialPort.get([callback])`
Returns the control flags (CTS, DSR, DCD) on the open port.
Uses [`GetCommModemStatus`](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363258(v=vs.85).aspx) for windows and [`ioctl`](http://linux.die.net/man/4/tty_ioctl) for mac and linux.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [callback] | <code>[modemBitsCallback](#module_serialport--SerialPort..modemBitsCallback)</code> | Called once the modem bits have been retrieved. |


-

<a name="module_serialport--SerialPort+flush"></a>

### `serialPort.flush([callback])`
Flush discards data received but not read and written but not transmitted. For more technical details see [`tcflush(fd, TCIFLUSH)`](http://linux.die.net/man/3/tcflush) for Mac/Linux and [`FlushFileBuffers`](http://msdn.microsoft.com/en-us/library/windows/desktop/aa364439) for Windows.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [callback] | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called once the flush operation finishes. |


-

<a name="module_serialport--SerialPort+drain"></a>

### `serialPort.drain([callback])`
Waits until all output data has been transmitted to the serial port. See [`tcdrain()`](http://linux.die.net/man/3/tcdrain) or [FlushFileBuffers()](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364439(v=vs.85).aspx) for more information.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [callback] | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called once the drain operation returns. |

**Example**  
Writes `data` and waits until it has finish transmitting to the target serial port before calling the callback.

```js
function writeAndDrain (data, callback) {
  sp.write(data, function () {
    sp.drain(callback);
  });
}
```

-

<a name="module_serialport--SerialPort+pause"></a>

### `serialPort.pause()` ⇒
The `pause()` method will cause a stream in flowing mode to stop emitting 'data' events, switching out of flowing mode. Any data that becomes available will remain in the internal buffer.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Returns**: `this`  
**See**: module:serialport#resume  

-

<a name="module_serialport--SerialPort+resume"></a>

### `serialPort.resume()` ⇒
The `resume()` method causes an explicitly paused Readable stream to resume emitting 'data' events, switching the stream into flowing mode.

**Kind**: instance method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Returns**: `this`  
**See**: module:serialport#pause  

-

<a name="module_serialport--SerialPort+event_error"></a>

### `Event: "error"`
The `error` event's callback is called with an error object whenever there is an error.

**Kind**: event emitted by <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

-

<a name="module_serialport--SerialPort+event_open"></a>

### `Event: "open"`
The `open` event's callback is called with no arguments when the port is opened and ready for writing. This happens if you have the constructor open immediately (which opens in the next tick) or if you open the port manually with `open()`. See [Useage/Opening a Port](#opening-a-port) for more information.

**Kind**: event emitted by <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

-

<a name="module_serialport--SerialPort+event_data"></a>

### `Event: "data"`
The `data` event puts the port in flowing mode. data will be emitted as soon as it's received. Data will be a `Buffer` object with a varying amount of data in it. The `readLine` parser converts the data into string lines. See the [parsers](#module_serialport--SerialPort.parsers) section for more information on parsers and the [NodeJS stream documentation](https://nodejs.org/api/stream.html#stream_event_data) for more information on the data event.

**Kind**: event emitted by <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

-

<a name="module_serialport--SerialPort+event_disconnect"></a>

### `Event: "disconnect"`
The `disconnect` event's callback is called with an error object. This will always happen before a `close` event if a disconnection is detected.

**Kind**: event emitted by <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

-

<a name="module_serialport--SerialPort+event_close"></a>

### `Event: "close"`
The `close` event's callback is called with no arguments when the port is closed. In the event of an error, an error event will be triggered

**Kind**: event emitted by <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

-

<a name="module_serialport--SerialPort.Binding"></a>

### `SerialPort.Binding` : <code>[Binding](#module_serialport--SerialPort..Binding)</code>
The Binding is how node SerialPort talks to the underlying system. By default we auto detect windows, Linux and OSX and load the appropriate module for your system. You can assign `SerialPort.Binding` to any backend you like. You can find more by searching on [npm](https://npmjs.org/).

  You can also avoid auto loading the default backends by requiring SerialPort with
  ```js
  var SerialPort = require('serialport/lib/serialport');
  SerialPort.Binding = MyBindingClass;
  ```

**Kind**: static property of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

-

<a name="module_serialport--SerialPort.parsers"></a>

### `SerialPort.parsers` : <code>object</code>
The default Parsers are [Transform streams](https://nodejs.org/api/stream.html#stream_class_stream_transform) that will parse data in a variety of ways and can be used to process incoming data.

 To use any of the parsers you need to create them and then pipe the serialport to the parser. Be sure not to write to the parser but to the SerialPort object.

**Kind**: static property of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| ByteLength | <code>Class</code> | is a transform stream that emits data as a buffer after a specific number of bytes are received. |
| Delimiter | <code>Class</code> | is a transform stream that emits data each time a byte sequence is received. |
| Readline | <code>Class</code> | is a transform stream that emits data after a newline delimiter is received. |

**Example**  
```js
var SerialPort = require('serialport');
var Readline = SerialPort.parsers.Readline;
var port = new SerialPort('/dev/tty-usbserial1');
var parser = new Readline();
port.pipe(parser);
parser.on('data', console.log);
port.write('ROBOT PLEASE RESPOND\n');

// creating the parser and piping can be shortened to
var parser = port.pipe(new Readline());
```

To use the byte length parser, you must provide the length of the number of bytes:
```js
var SerialPort = require('serialport');
var ByteLength = SerialPort.parsers.ByteLength
var port = new SerialPort('/dev/tty-usbserial1');
var parser = port.pipe(new ByteLength({length: 8}));
parser.on('data', console.log);
```

To use the Delimiter parser you must specify, you must provide a delimiter as a string, buffer, or an array of bytes:
```js
var SerialPort = require('serialport');
var Delimiter = SerialPort.parsers.Delimiter;
var port = new SerialPort('/dev/tty-usbserial1');
var parser = port.pipe(new Delimiter({delimiter: new Buffer('EOL')}));
parser.on('data', console.log);
```

To use the Readline parser, you may provide a delimiter (defaults to '\n')
```js
var SerialPort = require('serialport');
var Readline = SerialPort.parsers.Readline;
var port = new SerialPort('/dev/tty-usbserial1');
var parser = port.pipe(Readline({delimiter: '\r\n'}));
parser.on('data', console.log);
```

-

<a name="module_serialport--SerialPort.list"></a>

### `SerialPort.list(callback)` : <code>function</code>
Retrieves a list of available serial ports with metadata. Only the `comName` is guaranteed, all the other fields will be undefined if they are unavailable. The `comName` is either the path or an identifier (eg `COM1`) used to open the serialport.

**Kind**: static method of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type |
| --- | --- |
| callback | <code>listCallback</code> | 

**Example**  
```js
// example port information
{
  comName: '/dev/cu.usbmodem1421',
  manufacturer: 'Arduino (www.arduino.cc)',
  serialNumber: '757533138333964011C1',
  pnpId: undefined,
  locationId: '0x14200000',
  vendorId: '0x2341',
  productId: '0x0043'
}

```

```js
var SerialPort = require('serialport');
SerialPort.list(function (err, ports) {
  ports.forEach(function(port) {
    console.log(port.comName);
    console.log(port.pnpId);
    console.log(port.manufacturer);
  });
});
```

-

<a name="module_serialport--SerialPort..Binding"></a>

### SerialPort~Binding : <code>Class</code>
**Kind**: inner class of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| isOpen | <code>boolean</code> | Required property. `true` if the port is open, `false` otherwise. Should be read only. |


* [~Binding](#module_serialport--SerialPort..Binding) : <code>Class</code>
    * [`new Binding(options)`](#new_module_serialport--SerialPort..Binding_new)
    * [`.list(callback)`](#module_serialport--SerialPort..Binding+list)
    * [`.open(path, openOptions, openCallback)`](#module_serialport--SerialPort..Binding+open)
    * [`.close(callback)`](#module_serialport--SerialPort..Binding+close)
    * [`.read(data, length, readCallback)`](#module_serialport--SerialPort..Binding+read)
    * [`.write(data, writeCallback)`](#module_serialport--SerialPort..Binding+write)
    * [`.set([options], callback)`](#module_serialport--SerialPort..Binding+set)
    * [`.get([callback])`](#module_serialport--SerialPort..Binding+get)
    * [`.flush(callback)`](#module_serialport--SerialPort..Binding+flush)
    * [`.drain(callback)`](#module_serialport--SerialPort..Binding+drain)


-

<a name="new_module_serialport--SerialPort..Binding_new"></a>

#### `new Binding(options)`
You wont ever have to use Binding objects directly they'll be used by SerialPort to access the underlying hardware. This documentation is geared towards people making bindings for different platforms.

**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> |  |
| options.disconnect | <code>function</code> | function to be called when the bindings have detected a disconnected port. This function should be called during any operation instead of that operations usual callback. The `SerialPort` class will attempt to call `close` after a disconnection and ignore any errors. |


-

<a name="module_serialport--SerialPort..Binding+list"></a>

#### `binding.list(callback)`
Retrieves a list of available serial ports with metadata. The `comName` must be guaranteed and all the other fields should be undefined if they are unavailable. The `comName` is either the path or an identifier (eg `COM1`) used to open the serialport.

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  

| Param | Type |
| --- | --- |
| callback | <code>[listCallback](#module_serialport--SerialPort..listCallback)</code> | 


-

<a name="module_serialport--SerialPort..Binding+open"></a>

#### `binding.open(path, openOptions, openCallback)`
Opens a connection to the serial port referenced by the path.

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| path | <code>string</code> |  |
| openOptions | <code>[openOptions](#module_serialport--SerialPort..openOptions)</code> |  |
| openCallback | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | is called after the data has been passed to the operating system for writing. This will only be called when there isn't a pending write operation. |


-

<a name="module_serialport--SerialPort..Binding+close"></a>

#### `binding.close(callback)`
Closes an open connection

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| callback | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called once a connection is closed. |


-

<a name="module_serialport--SerialPort..Binding+read"></a>

#### `binding.read(data, length, readCallback)`
Request a number of bytes from the SerialPort. This function is similar to node's [`fs.read`](http://nodejs.org/api/fs.html#fs_fs_read_fd_buffer_offset_length_position_callback).

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.

**Params**: <code>integer</code> offset - is the offset in the buffer to start writing at.  

| Param | Type | Description |
| --- | --- | --- |
| data | <code>buffer</code> | Accepts a [`Buffer`](http://nodejs.org/api/buffer.html) object. |
| length | <code>integer</code> | specifying the maximum number of bytes to read. |
| readCallback | <code>[readCallback](#module_serialport--SerialPort..readCallback)</code> | is called after a read operation |


-

<a name="module_serialport--SerialPort..Binding+write"></a>

#### `binding.write(data, writeCallback)`
Write a number of bytes to the SerialPort

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| data | <code>buffer</code> | Accepts a [`Buffer`](http://nodejs.org/api/buffer.html) object. |
| writeCallback | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | is called after the data has been passed to the operating system for writing. This will only be called when there isn't a pending write operation. |


-

<a name="module_serialport--SerialPort..Binding+set"></a>

#### `binding.set([options], callback)`
Set control flags on an open port.

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [options] | <code>object</code> |  | All options are operating system default when the port is opened. Every flag is set on each call to the provided or default values. All options will always be provided. |
| [options.brk] | <code>Boolean</code> | <code>false</code> |  |
| [options.cts] | <code>Boolean</code> | <code>false</code> |  |
| [options.dsr] | <code>Boolean</code> | <code>false</code> |  |
| [options.dtr] | <code>Boolean</code> | <code>true</code> |  |
| [options.rts] | <code>Boolean</code> | <code>true</code> |  |
| callback | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> |  | Called once the port's flags have been set. |


-

<a name="module_serialport--SerialPort..Binding+get"></a>

#### `binding.get([callback])`
Get the control flags (CTS, DSR, DCD) on the open port.

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| [callback] | <code>[modemBitsCallback](#module_serialport--SerialPort..modemBitsCallback)</code> | Called once the flags have been retrieved. |


-

<a name="module_serialport--SerialPort..Binding+flush"></a>

#### `binding.flush(callback)`
Flush (discard) data received but not read and written but not transmitted.

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| callback | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called once the flush operation finishes. |


-

<a name="module_serialport--SerialPort..Binding+drain"></a>

#### `binding.drain(callback)`
Drain waits until all output data has been transmitted to the serial port.

**Kind**: instance method of <code>[Binding](#module_serialport--SerialPort..Binding)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| callback | <code>[errorCallback](#module_serialport--SerialPort..errorCallback)</code> | Called once the drain operation finishes. |


-

<a name="module_serialport--SerialPort..readCallback"></a>

### `SerialPort~readCallback` : <code>function</code>
A callback called with an error or null.

**Kind**: inner typedef of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Throws**:

- <code>TypeError</code> When given invalid arguments a TypeError will be thrown.


| Param | Type | Description |
| --- | --- | --- |
| error | <code>error</code> |  |
| bytesRead | <code>integer</code> | the number of bytes that have been written into the buffer |
| buffer | <code>buffer</code> | the buffer that data was written into, same object that was passed into `read`. |


-

<a name="module_serialport--SerialPort..errorCallback"></a>

### `SerialPort~errorCallback` : <code>function</code>
A callback called with an error or null.

**Kind**: inner typedef of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type |
| --- | --- |
| error | <code>error</code> | 


-

<a name="module_serialport--SerialPort..modemBitsCallback"></a>

### `SerialPort~modemBitsCallback` : <code>function</code>
A callback called with an error or an object with the modem line values (cts, dsr, dcd).

**Kind**: inner typedef of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type | Default |
| --- | --- | --- |
| error | <code>error</code> |  | 
| status | <code>object</code> |  | 
| [status.cts] | <code>boolean</code> | <code>false</code> | 
| [status.dsr] | <code>boolean</code> | <code>false</code> | 
| [status.dcd] | <code>boolean</code> | <code>false</code> | 


-

<a name="module_serialport--SerialPort..openOptions"></a>

### `SerialPort~openOptions` : <code>Object</code>
**Kind**: inner typedef of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  
**Properties**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| Binding | <code>[Binding](#new_module_serialport--SerialPort..Binding_new)</code> |  | The hardware access binding, The Binding is how node SerialPort talks to the underlying system. By default we auto detect windows, Linux and OSX and load the appropriate module for your system. |
| autoOpen | <code>boolean</code> | <code>true</code> | Automatically opens the port on `nextTick` |
| lock | <code>boolean</code> | <code>true</code> | Prevent other processes from opening the port. false is not currently supported on windows. |
| baudRate | <code>number</code> | <code>9600</code> | The baud rate of the port to be opened. This should match one of commonly available baud rates, such as 110, 300, 1200, 2400, 4800, 9600, 14400, 19200, 38400, 57600, 115200. There is no guarantee, that the device connected to the serial port will support the requested baud rate, even if the port itself supports that baud rate. |
| dataBits | <code>number</code> | <code>8</code> | Must be one of: 8, 7, 6, or 5. |
| stopBits | <code>number</code> | <code>1</code> | Must be one of: 1 or 2. |
| highWaterMark | <code>number</code> | <code>16384</code> | The size of the read and write buffers defaults to 16k |
| parity | <code>string</code> | <code>&quot;none&quot;</code> | Must be one of: 'none', 'even', 'mark', 'odd', 'space' |
| rtscts | <code>boolean</code> | <code>false</code> | flow control setting |
| xon | <code>boolean</code> | <code>false</code> | flow control setting |
| xoff | <code>boolean</code> | <code>false</code> | flow control setting |
| xany | <code>boolean</code> | <code>false</code> | flow control setting |
| platformOptions | <code>object</code> |  | sets platform specific options   // TODO handle these! |
| platformOptions.vmin | <code>number</code> | <code>1</code> | see [`man termios`](http://linux.die.net/man/3/termios) |
| platformOptions.vtime | <code>number</code> | <code>0</code> | see [`man termios`](http://linux.die.net/man/3/termios) |


-

<a name="module_serialport--SerialPort..listCallback"></a>

### `SerialPort~listCallback` : <code>function</code>
This callback type is called `requestCallback` and is displayed as a global symbol.

**Kind**: inner typedef of <code>[SerialPort](#exp_module_serialport--SerialPort)</code>  

| Param | Type | Description |
| --- | --- | --- |
| error | <code>error</code> |  |
| ports | <code>array</code> | an array of objects with port info. |


-


## Command Line Tools
If you install `serialport` globally. (eg, `npm install -g serialport`) you'll receive two command line tools.

### Serial Port List
`serialport-list` will list all available serial ports in different formats.

```bash
$ serialport-list -h

  Usage: serialport-list [options]

  List available serial ports

  Options:

    -h, --help           output usage information
    -V, --version        output the version number
    -f, --format <type>  Format the output as text, json, or jsonline. default: text


$ serialport-list
/dev/cu.Bluetooth-Incoming-Port
/dev/cu.usbmodem1421    Arduino (www.arduino.cc)

$ serialport-list -f json
[{"comName":"/dev/cu.Bluetooth-Incoming-Port"},{"comName":"/dev/cu.usbmodem1421","manufacturer":"Arduino (www.arduino.cc)","serialNumber":"752303138333518011C1","locationId":"0x14200000","vendorId":"0x2341","productId":"0x0043"}]

$ serialport-list -f jsonline
{"comName":"/dev/cu.Bluetooth-Incoming-Port"}
{"comName":"/dev/cu.usbmodem1421","manufacturer":"Arduino (www.arduino.cc)","serialNumber":"752303138333518011C1","locationId":"0x14200000","vendorId":"0x2341","productId":"0x0043"}
```

### Serial Port Terminal
`serialport-term provides a basic terminal interface for communicating over a serial port. `ctrl+c` will exit.

```bash
$ serialport-term -h

  Usage: serialport-term -p <port> [options]

  A basic terminal interface for communicating over a serial port. Pressing ctrl+c exits.

  Options:

    -h, --help                     output usage information
    -V, --version                  output the version number
    -l --list                      List available ports then exit
    -p, --port, --portname <port>  Path or Name of serial port
    -b, --baud <baudrate>          Baud rate default: 9600
    --databits <databits>          Data bits default: 8
    --parity <parity>              Parity default: none
    --stopbits <bits>              Stop bits default: 1
    --echo --localecho             Print characters as you type them.

$ serialport-term -l
/dev/cu.Bluetooth-Incoming-Port
/dev/cu.usbmodem1421    Arduino (www.arduino.cc)
```
