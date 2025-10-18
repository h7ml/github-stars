---
project: file-type
stars: 4136
description: Detect the file type of a file, stream, or data
url: https://github.com/sindresorhus/file-type
---

> Detect the file type of a file, stream, or data

The file type is detected by checking the magic number of the buffer.

This package is for detecting binary-based file formats, not text-based formats like `.txt`, `.csv`, `.svg`, etc.

We accept contributions for commonly used modern file formats, not historical or obscure ones. Open an issue first for discussion.

Install
-------

npm install file-type

**This package is an ESM package. Your project needs to be ESM too. Read more. For TypeScript + CommonJS, see `load-esm`.**

If you use it with Webpack, you need the latest Webpack version and ensure you configure it correctly for ESM.

File type detection is based on binary signatures (magic numbers) and should be treated as a best-effort hint, not a guarantee.

Usage
-----

### Node.js

Determine file type from a file:

import {fileTypeFromFile} from 'file-type';

console.log(await fileTypeFromFile('Unicorn.png'));
//=> {ext: 'png', mime: 'image/png'}

Determine file type from a Uint8Array/ArrayBuffer, which may be a portion of the beginning of a file:

import {fileTypeFromBuffer} from 'file-type';
import {readChunk} from 'read-chunk';

const buffer \= await readChunk('Unicorn.png', {length: 4100});

console.log(await fileTypeFromBuffer(buffer));
//=> {ext: 'png', mime: 'image/png'}

Determine file type from a stream:

import fs from 'node:fs';
import {fileTypeFromStream} from 'file-type';

const stream \= fs.createReadStream('Unicorn.mp4');

console.log(await fileTypeFromStream(stream));
//=> {ext: 'mp4', mime: 'video/mp4'}

The stream method can also be used to read from a remote location:

import got from 'got';
import {fileTypeFromStream} from 'file-type';

const url \= 'https://upload.wikimedia.org/wikipedia/en/a/a9/Example.jpg';

const stream \= got.stream(url);

console.log(await fileTypeFromStream(stream));
//=> {ext: 'jpg', mime: 'image/jpeg'}

Another stream example:

import stream from 'node:stream';
import fs from 'node:fs';
import crypto from 'node:crypto';
import {fileTypeStream} from 'file-type';

const read \= fs.createReadStream('encrypted.enc');
const decipher \= crypto.createDecipheriv(alg, key, iv);

const streamWithFileType \= await fileTypeStream(stream.pipeline(read, decipher));

console.log(streamWithFileType.fileType);
//=> {ext: 'mov', mime: 'video/quicktime'}

const write \= fs.createWriteStream(\`decrypted.${streamWithFileType.fileType.ext}\`);
streamWithFileType.pipe(write);

### Browser

import {fileTypeFromStream} from 'file-type';

const url \= 'https://upload.wikimedia.org/wikipedia/en/a/a9/Example.jpg';

const response \= await fetch(url);
const fileType \= await fileTypeFromStream(response.body);

console.log(fileType);
//=> {ext: 'jpg', mime: 'image/jpeg'}

API
---

### fileTypeFromBuffer(buffer, options)

Detect the file type of a `Uint8Array`, or `ArrayBuffer`.

The file type is detected by checking the magic number of the buffer.

If file access is available, it is recommended to use `fileTypeFromFile()` instead.

Returns a `Promise` for an object with the detected file type:

-   `ext` - One of the supported file types
-   `mime` - The MIME type

Or `undefined` when there is no match.

#### buffer

Type: `Uint8Array | ArrayBuffer`

A buffer representing file data. It works best if the buffer contains the entire file. It may work with a smaller portion as well.

### fileTypeFromFile(filePath, options)

Detect the file type of a file path.

This is for Node.js only.

To read from a `File`, see `fileTypeFromBlob()`.

The file type is detected by checking the magic number of the buffer.

Returns a `Promise` for an object with the detected file type:

-   `ext` - One of the supported file types
-   `mime` - The MIME type

Or `undefined` when there is no match.

#### filePath

Type: `string`

The file path to parse.

### fileTypeFromStream(stream)

Detect the file type of a web `ReadableStream`.

If the engine is Node.js, this may also be a Node.js `stream.Readable`.

Direct support for Node.js streams will be dropped in the future, when Node.js streams can be converted to Web streams (see `toWeb()`).

The file type is detected by checking the magic number of the buffer.

Returns a `Promise` for an object with the detected file type:

-   `ext` - One of the supported file types
-   `mime` - The MIME type

Or `undefined` when there is no match.

#### stream

Type: Web `ReadableStream` or Node.js `stream.Readable`

A readable stream representing file data.

### fileTypeFromBlob(blob, options)

Detect the file type of a `Blob`,

Tip

A `File` object is a `Blob` and can be passed in here.

It will **stream** the underlying Blob.

The file type is detected by checking the magic number of the blob.

Returns a `Promise` for an object with the detected file type:

-   `ext` - One of the supported file types
-   `mime` - The MIME type

Or `undefined` when there is no match.

import {fileTypeFromBlob} from 'file-type';

const blob \= new Blob(\['<?xml version="1.0" encoding="ISO-8859-1" ?>'\], {
	type: 'text/plain',
	endings: 'native'
});

console.log(await fileTypeFromBlob(blob));
//=> {ext: 'txt', mime: 'text/plain'}

Warning

This method depends on ReadableStreamBYOBReader which **requires Node.js ≥ 20** and may not be available in all modern browsers.

To work around this limitation, you can use an alternative approach to read and process the `Blob` without relying on streaming:

import {fileTypeFromBuffer} from 'file-type';

async function readFromBlobWithoutStreaming(blob) {
	const buffer \= await blob.arrayBuffer();
	return fileTypeFromBuffer(buffer);
}

#### blob

Type: `Blob`

### fileTypeFromTokenizer(tokenizer, options)

Detect the file type from an `ITokenizer` source.

This method is used internally, but can also be used for a special "tokenizer" reader.

A tokenizer propagates the internal read functions, allowing alternative transport mechanisms, to access files, to be implemented and used.

Returns a `Promise` for an object with the detected file type:

-   `ext` - One of the supported file types
-   `mime` - The MIME type

Or `undefined` when there is no match.

An example is `@tokenizer/http`, which requests data using HTTP-range-requests. A difference with a conventional stream and the _tokenizer_, is that it can _ignore_ (seek, fast-forward) in the stream. For example, you may only need and read the first 6 bytes, and the last 128 bytes, which may be an advantage in case reading the entire file would take longer.

import {makeTokenizer} from '@tokenizer/http';
import {fileTypeFromTokenizer} from 'file-type';

const audioTrackUrl \= 'https://test-audio.netlify.com/Various%20Artists%20-%202009%20-%20netBloc%20Vol%2024\_%20tiuqottigeloot%20%5BMP3-V2%5D/01%20-%20Diablo%20Swing%20Orchestra%20-%20Heroines.mp3';

const httpTokenizer \= await makeTokenizer(audioTrackUrl);
const fileType \= await fileTypeFromTokenizer(httpTokenizer);

console.log(fileType);
//=> {ext: 'mp3', mime: 'audio/mpeg'}

Or use `@tokenizer/s3` to determine the file type of a file stored on Amazon S3:

import {S3Client} from '@aws-sdk/client-s3';
import {makeChunkedTokenizerFromS3} from '@tokenizer/s3';
import {fileTypeFromTokenizer} from 'file-type';

// Initialize the S3 client
// Initialize S3 client
const s3 \= new S3Client();

// Initialize the S3 tokenizer.
const s3Tokenizer \= await makeChunkedTokenizerFromS3(s3, {
	Bucket: 'affectlab',
	Key: '1min\_35sec.mp4'
});

// Figure out what kind of file it is.
const fileType \= await fileTypeFromTokenizer(s3Tokenizer);
console.log(fileType);

Note that only the minimum amount of data required to determine the file type is read (okay, just a bit extra to prevent too many fragmented reads).

#### tokenizer

Type: `ITokenizer`

A file source implementing the tokenizer interface.

### fileTypeStream(webStream, options?)

Returns a `Promise` which resolves to the original readable stream argument, but with an added `fileType` property, which is an object like the one returned from `fileTypeFromFile()`.

This method can be handy to put in between a stream, but it comes with a price. Internally `stream()` builds up a buffer of `sampleSize` bytes, used as a sample, to determine the file type. The sample size impacts the file detection resolution. A smaller sample size will result in lower probability of the best file type detection.

**Note:** When using Node.js, a `stream.Readable` may be provided as well.

#### readableStream

Type: `stream.Readable`

#### options

Type: `object`

Supports the following options in addition to the general options:

##### sampleSize

Type: `number`  
Default: `4100`

The sample size in bytes.

#### Example

import got from 'got';
import {fileTypeStream} from 'file-type';

const url \= 'https://upload.wikimedia.org/wikipedia/en/a/a9/Example.jpg';

const stream1 \= got.stream(url);
const stream2 \= await fileTypeStream(stream1, {sampleSize: 1024});

if (stream2.fileType?.mime \=== 'image/jpeg') {
	// stream2 can be used to stream the JPEG image (from the very beginning of the stream)
}

#### readableStream

Type: `stream.Readable`

The input stream.

### supportedExtensions

Returns a `Set<string>` of supported file extensions.

### supportedMimeTypes

Returns a `Set<string>` of supported MIME types.

### Options

#### customDetectors

Array of custom file type detectors to run before default detectors.

For example:

import {fileTypeFromFile} from 'file-type';
import {detectXml} from '@file-type/xml';

const fileType \= await fileTypeFromFile('sample.kml', {customDetectors: \[detectXml\]});
console.log(fileType);

#### mpegOffsetTolerance

Default: `0`

Specifies the byte tolerance for locating the first MPEG audio frame (e.g. `.mp1`, `.mp2`, `.mp3`, `.aac`).

Allows detection to handle slight sync offsets between the expected and actual frame start. Common in malformed or incorrectly muxed files, which, while technically invalid, do occur in the wild.

A tolerance of 10 bytes covers most cases.

Custom detectors
----------------

Custom file type detectors are plugins designed to extend the default detection capabilities. They allow support for uncommon file types, non-binary formats, or customized detection behavior.

Detectors can be added via the constructor options or by modifying `FileTypeParser#detectors` directly. Detectors provided through the constructor are executed before the default ones.

Detectors can be added via the constructor options or by directly modifying `FileTypeParser#detectors`.

### Example adding a detector

For example:

import {FileTypeParser} from 'file-type';
import {detectXml} from '@file-type/xml';

const parser \= new FileTypeParser({customDetectors: \[detectXml\]});
const fileType \= await parser.fromFile('sample.kml');
console.log(fileType);

### Available third-party file-type detectors

-   @file-type/av: Improves detection of audio and video file formats, with accurate differentiation between the two
-   @file-type/xml: Detects common XML file types, such as GLM, KML, MusicXML, RSS, SVG, and XHTML

### Detector execution flow

If a detector returns `undefined`, the following rules apply:

1.  **No Tokenizer Interaction**: If the detector does not modify the tokenizer's position, the next detector in the sequence is executed.
2.  **Tokenizer Interaction**: If the detector modifies the tokenizer's position (`tokenizer.position` is advanced), no further detectors are executed. In this case, the file type remains `undefined`, as subsequent detectors cannot evaluate the content. This is an exceptional scenario, as it prevents any other detectors from determining the file type.

### Writing your own custom detector

Below is an example of a custom detector array. This can be passed to the `FileTypeParser` via the `fileTypeOptions` argument.

import {FileTypeParser} from 'file-type';

const unicornDetector \= {
	id: 'unicorn', // May be used to recognize the detector in the detector list
  	async detect(tokenizer) {
		const unicornHeader \= \[85, 78, 73, 67, 79, 82, 78\]; // "UNICORN" in ASCII decimal

		const buffer \= new Uint8Array(unicornHeader.length);
		await tokenizer.peekBuffer(buffer, {length: unicornHeader.length, mayBeLess: true});
		if (unicornHeader.every((value, index) \=> value \=== buffer\[index\])) {
			return {ext: 'unicorn', mime: 'application/unicorn'};
		}

		return undefined;
	}
}

const buffer \= new Uint8Array(\[85, 78, 73, 67, 79, 82, 78\]);
const parser \= new FileTypeParser({customDetectors: \[unicornDetector\]});
const fileType \= await parser.fromBuffer(buffer);
console.log(fileType); // {ext: 'unicorn', mime: 'application/unicorn'}

/\*\*
@param tokenizer - The \[tokenizer\](https://github.com/Borewit/strtok3#tokenizer) used to read file content.
@param fileType - The file type detected by standard or previous custom detectors, or \`undefined\` if no match is found.
@returns The detected file type, or \`undefined\` if no match is found.
\*/
export type Detector \= (tokenizer: ITokenizer, fileType?: FileTypeResult) \=> Promise<FileTypeResult | undefined\>;

Abort signal
------------

Some async operations can be aborted by passing an `AbortSignal` to the `FileTypeParser` constructor.

import {FileTypeParser} from 'file-type';

const abortController \= new AbortController()

const parser \= new FileTypeParser({abortSignal: abortController.signal});

const promise \= parser.fromStream(blob.stream());

abortController.abort(); // Abort file-type reading from the Blob stream.

Supported file types
--------------------

-   `3g2` - Multimedia container format defined by the 3GPP2 for 3G CDMA2000 multimedia services
-   `3gp` - Multimedia container format defined by the Third Generation Partnership Project (3GPP) for 3G UMTS multimedia services
-   `3mf` - 3D Manufacturing Format
-   `7z` - 7-Zip archive
-   `Z` - Unix Compressed File
-   `aac` - Advanced Audio Coding
-   `ac3` - ATSC A/52 Audio File
-   `ace` - ACE archive
-   `aif` - Audio Interchange file
-   `alias` - macOS Alias file
-   `amr` - Adaptive Multi-Rate audio codec
-   `ape` - Monkey's Audio
-   `apk` - Android package format
-   `apng` - Animated Portable Network Graphics
-   `ar` - Archive file
-   `arj` - Archive file
-   `arrow` - Columnar format for tables of data
-   `arw` - Sony Alpha Raw image file
-   `asar` - Archive format primarily used to enclose Electron applications
-   `asf` - Advanced Systems Format
-   `avi` - Audio Video Interleave file
-   `avif` - AV1 Image File Format
-   `avro` - Object container file developed by Apache Avro
-   `blend` - Blender project
-   `bmp` - Bitmap image file
-   `bpg` - Better Portable Graphics file
-   `bz2` - Archive file
-   `cab` - Cabinet file
-   `cfb` - Compound File Binary Format
-   `chm` - Microsoft Compiled HTML Help
-   `class` - Java class file
-   `cpio` - Cpio archive
-   `cr2` - Canon Raw image file (v2)
-   `cr3` - Canon Raw image file (v3)
-   `crx` - Google Chrome extension
-   `cur` - Icon file
-   `dat` - Windows registry hive file
-   `dcm` - DICOM Image File
-   `deb` - Debian package
-   `dmg` - Apple Disk Image
-   `dng` - Adobe Digital Negative image file
-   `docm` - Microsoft Word macro-enabled document
-   `docx` - Microsoft Word document
-   `dotm` - Microsoft Word macro-enabled template
-   `dotx` - Microsoft Word template
-   `drc` - Google's Draco 3D Data Compression
-   `dsf` - Sony DSD Stream File (DSF)
-   `dwg` - Autodesk CAD file
-   `elf` - Unix Executable and Linkable Format
-   `eot` - Embedded OpenType font
-   `eps` - Encapsulated PostScript
-   `epub` - E-book file
-   `exe` - Executable file
-   `f4a` - Audio-only ISO base media file format used by Adobe Flash Player
-   `f4b` - Audiobook and podcast ISO base media file format used by Adobe Flash Player
-   `f4p` - ISO base media file format protected by Adobe Access DRM used by Adobe Flash Player
-   `f4v` - ISO base media file format used by Adobe Flash Player
-   `fbx` - Filmbox is a proprietary file format used to provide interoperability between digital content creation apps.
-   `flac` - Free Lossless Audio Codec
-   `flif` - Free Lossless Image Format
-   `flv` - Flash video
-   `gif` - Graphics Interchange Format
-   `glb` - GL Transmission Format
-   `gz` - Archive file
-   `heic` - High Efficiency Image File Format
-   `icc` - ICC Profile
-   `icns` - Apple Icon image
-   `ico` - Windows icon file
-   `ics` - iCalendar
-   `indd` - Adobe InDesign document
-   `it` - Audio module format: Impulse Tracker
-   `j2c` - JPEG 2000
-   `jar` - Java archive
-   `jls` - Lossless/near-lossless compression standard for continuous-tone images
-   `jp2` - JPEG 2000
-   `jpg` - Joint Photographic Experts Group image
-   `jpm` - JPEG 2000
-   `jpx` - JPEG 2000
-   `jxl` - JPEG XL image format
-   `jxr` - Joint Photographic Experts Group extended range
-   `ktx` - OpenGL and OpenGL ES textures
-   `lnk` - Microsoft Windows file shortcut
-   `lz` - Archive file
-   `lz4` - Compressed archive created by one of a variety of LZ4 compression utilities
-   `lzh` - LZH archive
-   `m4a` - Audio-only MPEG-4 files
-   `m4b` - Audiobook and podcast MPEG-4 files, which also contain metadata including chapter markers, images, and hyperlinks
-   `m4p` - MPEG-4 files with audio streams encrypted by FairPlay Digital Rights Management as were sold through the iTunes Store
-   `m4v` - Video container format developed by Apple, which is very similar to the MP4 format
-   `macho` - Mach-O binary format
-   `mid` - Musical Instrument Digital Interface file
-   `mie` - Dedicated meta information format which supports storage of binary as well as textual meta information
-   `mj2` - Motion JPEG 2000
-   `mkv` - Matroska video file
-   `mobi` - Mobipocket
-   `mov` - QuickTime video file
-   `mp1` - MPEG-1 Audio Layer I
-   `mp2` - MPEG-1 Audio Layer II
-   `mp3` - Audio file
-   `mp4` - MPEG-4 Part 14 video file
-   `mpc` - Musepack (SV7 & SV8)
-   `mpg` - MPEG-1 file
-   `mts` - MPEG-2 Transport Stream, both raw and Blu-ray Disc Audio-Video (BDAV) versions
-   `mxf` - Material Exchange Format
-   `nef` - Nikon Electronic Format image file
-   `nes` - Nintendo NES ROM
-   `odg` - OpenDocument for drawing
-   `odp` - OpenDocument for presentations
-   `ods` - OpenDocument for spreadsheets
-   `odt` - OpenDocument for word processing
-   `oga` - Audio file
-   `ogg` - Audio file
-   `ogm` - Audio file
-   `ogv` - Audio file
-   `ogx` - Audio file
-   `opus` - Audio file
-   `orf` - Olympus Raw image file
-   `otf` - OpenType font
-   `otg` - OpenDocument template for drawing
-   `otp` - OpenDocument template for presentations
-   `ots` - OpenDocument template for spreadsheets
-   `ott` - OpenDocument template for word processing
-   `parquet` - Apache Parquet
-   `pcap` - Libpcap File Format
-   `pdf` - Portable Document Format
-   `pgp` - Pretty Good Privacy
-   `png` - Portable Network Graphics
-   `potm` - Microsoft PowerPoint macro-enabled template
-   `potx` - Microsoft PowerPoint template
-   `ppsm` - Office PowerPoint 2007 macro-enabled slide show
-   `ppsx` - Office PowerPoint 2007 slide show
-   `pptm` - Microsoft PowerPoint macro-enabled document
-   `pptx` - Microsoft PowerPoint document
-   `ps` - Postscript
-   `psd` - Adobe Photoshop document
-   `pst` - Personal Storage Table file
-   `qcp` - Tagged and chunked data
-   `raf` - Fujifilm RAW image file
-   `rar` - Archive file
-   `reg` - Windows registry (entries) file format
-   `rm` - RealMedia
-   `rpm` - Red Hat Package Manager file
-   `rtf` - Rich Text Format
-   `rw2` - Panasonic RAW image file
-   `s3m` - Audio module format: ScreamTracker 3
-   `shp` - Geospatial vector data format
-   `skp` - SketchUp
-   `spx` - Audio file
-   `sqlite` - SQLite file
-   `stl` - Standard Tesselated Geometry File Format (ASCII only)
-   `swf` - Adobe Flash Player file
-   `tar` - Tape archive or tarball
-   `tar.gz` - Gzipped tape archive (tarball)
-   `tif` - Tagged Image file
-   `ttc` - TrueType Collection font
-   `ttf` - TrueType font
-   `vcf` - vCard
-   `voc` - Creative Voice File
-   `vsdx` - Microsoft Visio File
-   `vtt` - WebVTT File (for video captions)
-   `wasm` - WebAssembly intermediate compiled format
-   `wav` - Waveform Audio file
-   `webm` - Web video file
-   `webp` - Web Picture format
-   `woff` - Web Open Font Format
-   `woff2` - Web Open Font Format
-   `wv` - WavPack
-   `xcf` - eXperimental Computing Facility
-   `xlsm` - Microsoft Excel macro-enabled document
-   `xlsx` - Microsoft Excel document
-   `xltm` - Microsoft Excel macro-enabled template
-   `xltx` - Microsoft Excel template
-   `xm` - Audio module format: FastTracker 2
-   `xml` - eXtensible Markup Language
-   `xpi` - XPInstall file
-   `xz` - Compressed file
-   `zip` - Archive file
-   `zst` - Archive file

_Pull requests are welcome for additional commonly used file types._

The following file types will not be accepted:

-   MS-CFB: Microsoft Compound File Binary File Format based formats, too old and difficult to parse:
    -   `.doc` - Microsoft Word 97-2003 Document
    -   `.xls` - Microsoft Excel 97-2003 Document
    -   `.ppt` - Microsoft PowerPoint97-2003 Document
    -   `.msi` - Microsoft Windows Installer
-   `.csv` - Reason.
-   `.svg` - Supported by third-party detector.

#### tokenizer

Type: `ITokenizer`

Usable as source of the examined file.

#### fileType

Type: `FileTypeResult`

An object having an `ext` (extension) and `mime` (mime type) property.

Detected by the standard detections or a previous custom detection. Undefined if no matching fileTypeResult could be found.

Related
-------

-   file-type-cli - CLI for this module
-   image-dimensions - Get the dimensions of an image

Maintainers
-----------

-   Sindre Sorhus
-   Borewit
