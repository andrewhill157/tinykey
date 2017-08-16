# tinykey
I use Keynote a lot but the file sizes often get quite large.

Part of the reason is that Keynote stores imported images as TIFFs that are large in size. `tinypng` can reduce the size of TIFFs pretty dramatically without much dicernable change in quality.

# Usage
You can overwrite a file with:
```
./tinypng mykey.key
```

You can also output a new file if you are wary:
```
./tinypng mykey.key -o mynewkey.key
```

Note you must have `./` in front of the command, unless you put tinypng executable on your PATH, in which case you may just use `tinypng`.

# Requirements
You must have python 2.7+ or python 3.2+.

You must have [ImageMagick](https://www.imagemagick.org/script/index.php) installed. There are many ways to install, such as homebrew, macports, etc. For example, with homebrew:
```
brew install imagemagick
```
