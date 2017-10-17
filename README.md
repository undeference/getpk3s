# getpk3s
Manage your Tremulous maps (using https://betaserv.tk/paklist.html)

### SYNOPSIS
`getpk3s [VERB] [ARGS]…`

### VERBs
#### `init`
Initialize diretories for use with getpk3s

ARGS specifies a list of directories. If no directories are specified, init the current directory

This creates a SHA1SUMS file containing SHA-1 checksums of every *.pk3 file in each directory. It can be used as an argument to sha1sum's check flag (i.e., `sha1sum -c SHA1SUMS`)

#### `search`
Search for PK3s

ARGS specifies search terms. Different forms of search terms are interpreted differently

Terms composed of only 32 hexadecimal characters (i.e., containing only characters in the ranges 0-9 and A-F) are interpreted as MD5 checksums

Terms composed of only 40 hexadecimal characters are interpreted as SHA-1 checksums

Terms containing the string "://" are interpreted as absolute URLs to PK3s

Other terms are searched for in PK3 file names. "*" can be used as a wildcard

#### `install`
Install PK3s to the current directory matching search terms specified in ARGS (as described in **`search`**)

Note this will only install into the current directory and only if it has been `init`ialized first

#### `delete`
Delete specified files from the current directory

ARGS specifies a list of file names in the current directory. These files will be deleted and removed from the SHA1SUMS file

#### `verify`
Verify PK3s in specified directories

ARGS specifies a list of directories. If no directories are specified, verify the current directory

This does essentially the same thing as `sha1sum --quiet -c SHA1SUMS`

#### `help`
Shows a (very) concise description of VERBs

#### `TEST=1`

### COPYRIGHT
Copyright © M. Kristall

### LICENSE
This program is free software. You can redistribute and/or modify it under
the same terms as Tremulous (i.e., GNU General Public License version 2 or
later).
