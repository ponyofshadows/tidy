# tidy
a simply solution for organize files in home.

## directory tree
```
~
|__ .archive/
    |__ 240625archived_proj1
    |__ 240626archived_proj2
    |__ ...
|__ .usr/
    |__ bin/
    |__ src/
    |__ include/
    |__ books/
    |__ album/
    |__ ...
|__ file1
|__ proj1/
|__ proj2/
|__ ...
```

## Usage
1. Archive
```bash
# move to ~/.archive/, or move back to ~/
tidy -a ~/file1
tidy --achive proj1
```
2. Backup
- Depends on `rsync`
- Back up all non-dot files under `~` and files under `.usr/` 
```bash
tidy -r                     # rsync from `~` to `/mnt`
tidy --rsync /mnt/dir1      # rsync from `~` to `/mnt/dir1`  
tidy -r /mnt/dir1 /mnt/dir2 # rsync from `/mnt/dir1` to `/mnt/dir2` 
tidy -r --only-archive      # only rsync archives
```
