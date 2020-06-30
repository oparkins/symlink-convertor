# symlink-convertor
Converts dead symlinks into text files with target locations

## About

This was created to allow `gsutil` to upload directories that may contain bad links in them. The links can be important because it is how the data was processed earlier. 

So, when this program encounters a link, it will take the target link and put it in a text file. This will allow for the `rsync` feature of `gsutil` to work properly. 

## Installation

You can use `pip` to install the program:
```
pip3 install symlinkConverter
```

## Usage

```
usage: symlinkConverter [-h] [--dry-run] [--recursive] [--undo] target

Convert bad symlinks into rsync-able content

positional arguments:
  target           The directory to run in

optional arguments:
  -h, --help       show this help message and exit
  --dry-run, -n    Just list files that would be changed
  --recursive, -r  Run recursively
  --undo           Turn text files into symlinks
```

### Undo Operation

The undo flag will take any file with the correct extension and turn it back into a symlink.