# Evolving Music Collection Cleanup

This is a process for cleaning up a live music collection according to specific rules.

The file structure for live music is:

```
Artist/
  YEAR/
    YEAR.MON.DAY Venue, City, StateCode - Info
```

Likewise, the file structure for studio music is:

```
Artist/
  YEAR/
    YEAR AlbumName
```

## Installation

Install `ffmpeg`, `lame`, and `imagemagick`.

On Debian/Ubuntu Linux, do:

```
$ sudo apt-get install ffmpeg lame libmp3lame0 imagemagick
```

From this path, symlink `emcc` to user's bin directory:

```
ln -s `pwd`/emcc ~/bin/
```

### Updates

From this path, run:

```
git pull
```

## Usage

```
emcc [path] [mode] [bitrate]
```

### Path

The path is assumed to be a collection of artists defined as subdirectories.

```
/media/ExternalHD/Music/
  Band/
  Band 1/
  Band 2/
```

Any subdirectories containg characters aside from `A-Z` `0-9` or `,' &` will be automatically ignored.

Thus, folders can be skipped by naming something like: `Band - Unorganized` since the `-` will cause it to skip.

Thus, for this example, use:

```
emcc "/media/ExternalHD/Music"
```

### Mode

When `mode` is `0` or `blank`, the process will run in simulation and not make any changes.

However, when mode is `1`, changes will be made.

### Bitrate

Bitrate options are either `blank` which defaults to `256`, `256` or `320`.

`256` is encoded `V0` variable bitrate with `lame` encoder. `320` encodes to constant bitrate.

## Keep Certain Files in FLAC Format

By default the script converts high quality to good quality mp3, but to stop this from happening to `FLAC` files, create a file in the `path` directory named `.emcc-keep`.  Within this file, match what you want to skip like:

.emcc-keep
```
Band 1
Band 2/2000/2000.12.31 New Years
```

## Work-in-Progress

**_This script is currently a work-in-progress and is only advised to be run against a test directory._**
