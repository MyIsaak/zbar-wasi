# zbar-wasi

![Node.js CI](https://github.com/MyIsaak/zbar-wasi/workflows/Node.js%20CI/badge.svg)
![Code scanning - action](https://github.com/MyIsaak/zbar-wasi/workflows/Code%20scanning%20-%20action/badge.svg)
![npm (tag)](https://img.shields.io/npm/v/zbar-wasi/latest)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/MyIsaak/zbar-wasi/graphs/commit-activity)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Downloads Total](https://img.shields.io/npm/dt/zbar-wasi.svg)](https://www.npmjs.com/package/zbar-wasi)
[![Downloads Month](https://img.shields.io/npm/dm/zbar-wasi)](https://www.npmjs.com/package/zbar-wasi)

Scan barcodes in web browsers

This library allows web browsers to scan barcodes with a Webassembly and WASI backend.

## Why?

- Unlike most Webassembly projects this one is compiled with WASI instead of Emscripten.
- Optimized for size with a WASM binary size of 161.98 KB gzipped (244.40 KB uncompressed).
- Works perfectly on mobile devices and desktop

## Demo

Try scanning barcodes with your camera: https://myisaak.github.io/zbar-wasi/
Watch your command line for found barcodes.

## Installation

```
npm install zbar-wasi
```

## Usage

```js
import { scanImage, createZbar } from "zbar-wasi";

const start = async () => {
  // move ./node_modules/zbar-wasi/dist/zbar.wasm to your web directory"
  const ZBAR = await createZbar({ wasmpath: "./zbar.wasm" });
  const imageData = ctx.getImageData(0, 0, width, height);
  const results = scanImage(imageData);
  console.log(results);
  // outputs [ barcode1, barcode2, ... ]
}
start();
```
