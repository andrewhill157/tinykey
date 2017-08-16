# tinykey
I use Keynote a lot but the file sizes can sometimes get quite large (100+ MB).

One reason for some of my presentations is that Keynote sometimes stores imported/pasted images as TIFFs that can be quite large in size. `tinypng` can reduce the size of these TIFFs without any dicernable change in quality.

# Usage
You can overwrite a file with:
```
./tinypng mykey.key
```

You can also output a new file if you want to preserve the original file:
```
./tinypng mykey.key -o mynewkey.key
```

Note you must have `./` (if using tinypng from the directory you keep it in) or the full path to the tinypng executable in front of the command as shown above, unless you put the `tinypng` executable on your `PATH`, in which case you may just use `tinypng`.

# Requirements
You must have `python 2.7+` or `python 3.2+` installed.

You must have [ImageMagick](https://www.imagemagick.org/script/index.php) installed. There are many ways to install, such as homebrew, macports, etc. For example, with homebrew:
```
brew install imagemagick
```

# Disclamer
Note that `tinypng` will only reduce the size of your file if the cause is large TIFF images. For some of my large presentations this makes a huge difference (300MB -> 30 MB, for example), but your mileage may vary.

All `tinypng` is doing is converting the TIFF files to PNG and back using ImageMagick which often results in much smaller TIFF files.

Keynote also has `File > Advanced > Reduce File Size` (as well as other alternatives) that might also be of use to you. However, this performs PNG -> JPEG conversion which doesn't play nicely with text-heavy images.

# Running on Many Files
It is easy to compress lots of files on command line using `tinypng`:
```
for file in *.key; do tinypng $file; done
```

With a bit of bash programming you can also output to new files, run in background, etc.
