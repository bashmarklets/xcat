# xcat
I like `cat`.  It is a simple tool to concatenate the content of files to standard output.

If I deal with a gzip-compressed file, however, then I will be using the `zcat` command instead. If I am
inspecting a .bz2 file then I'll just use `bzcat`, cool. Oh and if I am to have a quick look and
grep through a .xz file then I'll use `xzcat`. Almost forgot that there's another tool in town
called `zstdcat` for doing the same for zstd compressed files. Ehh.

Often when I `cat` something I am not that fuzzed about the accuracy or completeness of the data;
I mostly just want to have a peak inside the file to get a feel for what it is about. For that very
same reason I kind of would like to also be able to do the same with MS Word .doc files getting
text instead of scrambled binary data. What about .pdf files? And what about .jpg images?

So I ended up creating `xcat`; one feline to rule them all by leveraging different tools (if they
are installed).

## How to install

Clone this repository and ensure that the directory containing the `xcat` file is in your PATH
environment variable.

Depending on your needs you may want to make sure that the following applications or packages are
installed:

```
cat, zcat, bzcat, lzip, arj, tar, 7z, pdftotext, exiftool, unoconv, ufraw-batch, convert
(imagemagick), jp2a, metaflac, lsd, source-highlight
```

## Disclaimer

This is clearly a work in progress and it is in very early stages. It is incomplete. Any of this is
subject to radical change or even re-write in another language. Consider it pre-alpha :)

Feedback and example files / suggestions for additional support would be very appreciated.

## Features

- handles compressed files (.tar, .bz, .bz2, .xz, .lz, .gz, .arj, .rar, .zst, .jar, .zip, and more)
    - lists files if archive contains more than one file (where applicable)
- runs a variety of scripts and code files through `source-highlight` for easier reading
- runs PDF files through `pdftotext` if installed
- runs a variety of document types, spreadsheets and presentation formats through `unoconv`
- extracts EXIF metadata from a variety of audio and video files using `exiftool`
- extracts metadata from FLAC files using `metaflac` if installed
- converts image files into ascii for a visual representation on the command line using `jp2a`
- lists directories using `lsd` if installed
- passing the `-f` (`--force`) parameter some times produces an alternative output of the same file
- gives basic information about the file if file type is not recognised (or if relevant
applications are not installed)
- can deduce file extension based on mime type in some situations
