# tesseract-ocr-build

Prebuilt tesseract binaries for use on Travis CI. The main motivation is that
tesseract included in Trusty is no longer supported by
[tesserocr](https://pypi.org/project/tesserocr/).

[![Build Status](https://travis-ci.com/nijel/tesseract-ocr-build.svg?branch=master)](https://travis-ci.com/nijel/tesseract-ocr-build)

## Available versions

* [3.04.01-1](https://github.com/nijel/tesseract-ocr-build/releases/download/3.04.01-1/tesseract.tar.xz) - tesseract 3.04.01 and leptonica 1.73
* [3.05.02-3](https://github.com/nijel/tesseract-ocr-build/releases/download/3.05.02-3/tesseract.tar.xz) - tesseract 3.05.02 and leptonica 1.76.0
* [4.0.0-beta.3-2](https://github.com/nijel/tesseract-ocr-build/releases/download/4.0.0-beta.3-2/tesseract.tar.xz) - tesseract 4.0.0-beta.3 and leptonica 1.76.0
* [4.0.0-beta.4-2](https://github.com/nijel/tesseract-ocr-build/releases/download/4.0.0-beta.4-2/tesseract.tar.xz) - tesseract 4.0.0-beta.4 and leptonica 1.76.0
* [4.0.0-rc1-1](https://github.com/nijel/tesseract-ocr-build/releases/download/4.0.0-rc1-1/tesseract.tar.xz) - tesseract 4.0.0-rc1 and leptonica 1.76.0
* [4.0.0-rc3-1](https://github.com/nijel/tesseract-ocr-build/releases/download/4.0.0-rc3-1/tesseract.tar.xz) - tesseract 4.0.0-rc3 and leptonica 1.76.0
* [4.0.0-1](https://github.com/nijel/tesseract-ocr-build/releases/download/4.0.0-1/tesseract.tar.xz) - tesseract 4.0.0 and leptonica 1.76.0
* [4.1.0-1](https://github.com/nijel/tesseract-ocr-build/releases/download/4.1.0-1/tesseract.tar.xz) - tesseract 4.1.0 and leptonica 1.78.0

Other tags are kept for reference only and are not recommended for usage.

## Usage

Put following into `.travis.yml`:

```yaml
install:
  - export TESSERACT_VERSION=4.0.0-1
  - export TESSERACT_INSTALL=$HOME/.tesseract
  - export TESSERACT_PKG=$TESSERACT_INSTALL/lib/pkgconfig
  - export LD_LIBRARY_PATH=$TESSERACT_INSTALL/lib:$LD_LIBRARY_PATH
  - export PKG_CONFIG_PATH=$TESSERACT_PKG:$PKG_CONFIG_PATH
  - wget -O - https://github.com/nijel/tesseract-ocr-build/releases/download/$TESSERACT_VERSION/tesseract.tar.xz | tar -C $HOME -xJf -
```

## Language data

The package contains English trained data, if you want to include more simply
place the files to the `$HOME/.tesseract/share/tessdata` folder.
