# node-memfs
Linear Memory exposed as filesystem to exchange data and messages in a performant way. low overhead ipc

## Usage

```
npm -i frank-dspeed/node-memfs
```
uses @direktspeed/node-fuse-bindings pre build binarys 


sharedArrayBufferFs.js
```js
const { createFs } from 'memfs'
const fs = createFs(options)
fs.mount() // returns OS: path: as file:/// url

fs.unmount()


const buffer = new ArrayBuffer(8); // Default Length 8 Bytes aka 8*8 = 64 bits
//const view = new Int32Array(buffer) // Length: 2 contains 2x 4 Bytes so 32 bits + 32 bits
```

## Examples
- Use it to power direct rendering on WebGPU
- Use it for Realtime in and Output without Network overhead. 
- Use it as IPC Message Exchange. from NodeJS to the Browser. 
- Use the IPC Example to interface with chromium via a extension on launch. 
  - the extension will use the fileSystemApi


```js
extension use https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getURL
message the url to the content
expose the extension on the memFS. https://developer.chrome.com/docs/extensions/mv3/manifest/web_accessible_resources/
```
