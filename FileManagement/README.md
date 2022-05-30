# File management 

## Common file types

There are seven types of files which are supported, for the RHSCA you only need
to concern yourself with the following:

- regular
- directory
- block special device
- character special device
- symbolic device 

#### regular files

All regular files are represented when outputed with a ls -l command start with
the a - for example:

```console
ls -l
-rw------- 1 root root 1225 27 May 15:27 example.txt
```

There are two more commands which you are able to run to get stats from a
regular file which are:

```console
file example.txt
stat example.txt
```

#### directory files

Are logical containers that hold files and subdirectories, you are able to tell
if a file is a directory from the ls command as it will strat with a d.
For example:

```console
ls -l
drw-xr-xr-x 2 root root 1225 27 May 15:27 example
```

#### block and character special device files

Each piece of the hardware within the system has an associated file in the /dev 
directory that is used by the system to communicate with that device.
This is known as a device file, there are two types of device files: character
and block. When running the ls -l command the beginning starts with c and b
respectively.

#### symbolic links

A symbolic link could be considered a shortcut to another file or directory. 
If you run the ls -l command on a symbolic link the line entry would start with
l and an arrow would be pointing to the target link.

## Compression and Archiving 

#### using gzip and gunzip

You are able to compress files using gzip and to unzip them you are able to use
gunzip, to get information about a file that has been gzipped you can use the 
following flag with the gzip command: -l. Here is an example of using gzip and 
gunzip:

```console
gzip example
    output -> example.gz
gunzip example.gz 
    output -> example
```

#### bzip2 and bunzip2

Is another compression command which can be used within linux, when compressing
with bzip2 the file will end with the extension .bz2. It works the same way as
gzip and gunzip.

> **note** the key difference between bzip2 and gzip is that bzip2 has a better
> compression ratio, but is slower. 

#### using tar (tape archive)

| option | definition                                                  |
|--------|-------------------------------------------------------------|
| -c     | creates a tarball                                           |
| -f     | specifies a tarball name                                    |
| -p     | preserce file permissions                                   |
| -r     | appends files to the end of an extant un compressed tarball |
| -t     | lists content of a tarball                                  | 
| -u     | appends files to the end of an extant uncompressed tarball  |
| -v     | verbose mode                                                |
| -x     | extracts or restores from a tarball                         |

> **note** -r and -u don't support adding files to an existing compressed 
> tarball

example command:

```console
tar -cvf example.tar example
```
> the above command would compress the file example and call it example.tar
> **tip** Archiving and compression are usually done together to produce smaller
> archive files

#### file and directory operations 

#### file linking
