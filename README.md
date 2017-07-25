# Evolving Music Collection Cleanup

This is a process for cleaning up a live music collection according to specific rules.

The file structure is as follows:

```
Artist/
  YEAR/
    YEAR.MON.DAY Venue, City, StateCode - Info
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
emcc [location]
```

## Work-in-Progress

**_This script is currently a work-in-progress and is only advised to be run against a test directory._**
