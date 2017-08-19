# tinykey
I use Keynote a lot but the file sizes can sometimes get quite large (100+ MB).

For some of my presentations, the reason seems to be that Keynote sometimes stores large imported/pasted images as TIFFs without reducing the file size at all. `tinypng` can reduce the size of these larger files without reducing image quality.

# Usage
You can overwrite a file with:
```
tinypng mykey.key
```

You can also output a new file if you want to preserve the original file:
```
tinypng mykey.key -o mynewkey.key
```

Note that unless you place this executable on your `PATH` you must run `./tinyping` (if using `tinypng` from the directory you keep it in) or the full path to the tinypng executable. If you have issues running as an executable, you may also use `python tinypng`.

# Requirements
You must have `python 2.7+` or `python 3.2+` installed.

You must have the [Pillow](http://python-pillow.org/) package installed. Please run:
```
pip install -r requirements.txt
```

or

```
pip install Pillow
```

# Disclamer
Note that `tinypng` will only reduce the size of your file if the cause is large images. For some of my large presentations this makes a huge difference (300MB -> 30 MB, for example), but your mileage may vary.

Keynote also has `File > Advanced > Reduce File Size` (as well as other alternatives) that might also be of use to you. However, this performs PNG -> JPEG conversion which doesn't play nicely with text-heavy images.

# Running on Many Files
It is easy to compress lots of files on command line using `tinypng`:
```
for file in *.key; do tinypng $file; done
```

With a bit of bash programming you can also output to new files, run in background, etc.
