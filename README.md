# Productvideo FFmpeg corresponding source

This repository distributes the corresponding source for the custom single-thread
FFmpeg/WebAssembly core used by the Shop-Script Productvideo plugin.

## Download

[Download the Productvideo 1.0.0 corresponding source archive](https://github.com/emmy-design/productvideo-ffmpeg-sources/releases/download/shop-productvideo-1.0.0/shop-productvideo-1.0.0-ffmpeg-sources.tar.gz)

[Release and SHA-256 checksum](https://github.com/emmy-design/productvideo-ffmpeg-sources/releases/tag/shop-productvideo-1.0.0)

The source archive contains FFmpeg and dependency source archives, the exact
build recipe and profile, and the source forms of the bundled Mediabunny,
fflate and Emscripten runtime components. Each component retains its own license
and copyright notices; see the source archive for the full license texts.

## Build identity

- Plugin version: 1.0.0
- FFmpeg: n5.1.4, ffmpeg.wasm core API 0.12.10
- Profile: shop-slim-v1, single thread
- Emscripten: 3.1.40
- Compiled WASM SHA-256: 74241d3db324b53060e15d7b916e16e9d99d46312d0fd517c70952ba674206d0
- Source archive: shop-productvideo-1.0.0-ffmpeg-sources.tar.gz
- Source SHA-256: ed5ee4c2a1c8d70e44b16b656cfd85f76f304c7ea5b9ee5895c38359304c8d84

## Rebuild

Extract the archive and run from its top-level directory:

```sh
python3 recipe/build.py --work-dir "$PWD/work" --output "$PWD/dist"
```

The recipe requires a native C/C++ compiler, make, autoconf, Perl, Python 3 and
Node.js. It downloads the pinned Emscripten compiler into the work directory;
no global installation is performed. The dependency source archives are included
and verified against their pinned hashes.

The FFmpeg core includes x264 and is distributed under GPL-2.0-or-later. The
Mediabunny source retains MPL-2.0; the other included components retain the terms
stated in their own license files. The wrapper's MIT license does not replace
the compiled FFmpeg core's GPL terms.
