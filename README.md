# tesseract-ocr-build

Prebuilt tesseract binaries for use on Travis CI. The main motivation is that
tesseract included in Trusty is no longer supported by
[tesserocr](https://pypi.org/project/tesserocr/).

[![Build Status](https://travis-ci.com/nijel/tesseract-ocr-build.svg?branch=master)](https://travis-ci.com/nijel/tesseract-ocr-build)

Usage (in `.travis.yml`):

```yaml
install:
  - export TESSERACT_INSTALL=$HOME/.tesseract
  - export TESSERACT_PKG=$TESSERACT_INSTALL/lib/pkgconfig
  - export LD_LIBRARY_PATH=$TESSERACT_INSTALL/lib:$LD_LIBRARY_PATH
  - export PKG_CONFIG_PATH=$TESSERACT_PKG:$PKG_CONFIG_PATH
  - export TESSDATA_PREFIX=/usr/share/tesseract-ocr/tessdata/
  - wget -O - https://github.com/nijel/tesseract-ocr-build/releases/download/3.05.02-3/tesseract.tar.xz | tar -C $HOME -xf -
```
