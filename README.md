# Evolving Music Collection Cleanup

This is a process for cleaning up a live music collection according to specific rules.

The file structure for live music is:

```
Music/
  Artist/
    YEAR/
      YEAR.MON.DAY Venue, City, StateCode - Info
```

Likewise, the file structure for studio music is:

```
Music/
  Artist/
    YEAR/
      YEAR Album
```

## Installation

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

### Mode

When `mode` is `0` or `blank`, the process will run in simulation and not make any changes.

However, when mode is `1`, changes will be made.

### Bitrate

Bitrate options are either `blank` which defaults to `256`, `256` or `320`.

`256` is encoded `V0` with `lame`.

## Work-in-Progress

**_This script is currently a work-in-progress and is only advised to be run against a test directory._**
