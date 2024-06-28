# tidy
a simply solution for organize files in home.

## directory tree
```
~
|__ archive/
    |__ 240625archived_proj1
    |__ 240626archived_proj2
    |__ ...
|__ .local/usr/
    |__ bin/
    |__ src/
    |__ include/
    |__ books/
    |__ album/
|__ proj1/
|__ proj2/
|__ file1
|__ ...
```

## Usage
1. Archive
```bash
# move to ~/archive/
tidy proj1
tidy ~/file1
tidy -a proj2
# reduce from archive to home
tidy -l         # list recent 10 archives
tidy -l keyword # find matched archives in this year    
tidy -r proj1   # reduce
tidy -r file1
tidy -r ~/archive/2406* # reduce archives in June 2024. 
```
2. Backup
- Depends on `rsync`
- backup all non-dotfile and `.local/usr` 
```bash
tidy -b # rsync from `~` to `/mnt`
tidy -o /mnt/dir1              # rsync from `~` to `/mnt/dir1`  
tidy -b /mnt/dir1 -o /mnt/dir2 # rsync from `/mnt/dir1` to `/mnt/dir2` 
tidy -b --only-archive         # only rsync archives
```
