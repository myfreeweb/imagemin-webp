# imagemin-webp [![Build Status](https://travis-ci.org/imagemin/imagemin-webp.svg?branch=master)](https://travis-ci.org/imagemin/imagemin-webp) [![Build status](https://ci.appveyor.com/api/projects/status/erd3nf73djfm4gjp?svg=true)](https://ci.appveyor.com/project/ShinnosukeWatanabe/imagemin-webp)

> WebP imagemin plugin


## Install

```
$ npm install --save imagemin-webp
```


## Usage

```js
const imagemin = require('imagemin');
const imageminWebp = require('imagemin-webp');

imagemin(['images/*.{jpg,png}'], 'build/images', {
    use: [
        imageminWebp({quality: 50})
    ]
}).then(() => {
    console.log('Images optimized');
});
```


## API

### imageminWebp([options])(buffer)

#### options

##### preset

Type: `string`<br>
Default: `default`

Preset setting, one of `default`, `photo`, `picture`, `drawing`, `icon` and `text`.

##### quality

Type: `number`<br>
Default: `75`

Set quality factor between `0` and `100`.

##### alphaQuality

Type: `number`<br>
Default: `100`

Set transparency-compression quality between `0` and `100`.

##### method

Type: `number`<br>
Default: `4`

Specify the compression method to use, between `0` (fastest) and `6` (slowest). This parameter controls the trade off between encoding speed and the compressed file size and quality.

##### size

Type: `number`<br>

Set target size in bytes.

##### sns

Type: `number`<br>
Default: `80`

Set the amplitude of spatial noise shaping between `0` and `100`.

##### filter

Type: `number`<br>

Set deblocking filter strength between `0` (off) and `100`.

##### autoFilter

Type: `boolean`<br>
Default: `false`<br>

Adjust filter strength automatically.

##### sharpness

Type: `number`<br>
Default: `0`

Set filter sharpness between `0` (sharpest) and `7` (least sharp).

##### lossless

Type: `boolean`<br>
Default: `false`

Encode images losslessly.

##### nearLossless

Type: `number`<br>
Default: `100`

Encode images losslessly with [an additional lossy pre-processing step](https://groups.google.com/a/webmproject.org/forum/#!msg/webp-discuss/0GmxDmlexek/3ggyYsaYdFEJ), with a quality factor between `0` (maximum pre-processing) and `100` (same as `lossless`).

##### crop

Type: `object { x, y, w, h: nubmer }`<br>

Crop the output picture.

##### resize

Type: `object { w, h: nubmer }`<br>

Resize the output picture (happens after crop if crop is also given).

#### buffer

Type: `buffer`

Buffer to optimize.


## License

MIT © [imagemin](https://github.com/imagemin)
