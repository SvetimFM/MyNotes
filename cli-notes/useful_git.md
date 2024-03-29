# Useful GIT


------------
### Command List

- [git rm -r --cached (remove file from remote only)](#Remove-file-from-remote-only)


------------
####  Remove file from remote only
#### `git rm -r --cached` 

The `git rm -r --cached` command is a powerful feature of Git, designed to **remove files or directories from the repository's index** while keeping the actual files safe in your working directory. This capability is incredibly helpful for correcting instances where files have been accidentally tracked and committed, but were meant to be ignored (as specified in `.gitignore`).

##### Key Options

- `-r`: Enables recursive removal, allowing directories and their contents to be untracked.
- `--cached`: Targets the removal action to the index only, ensuring that the working tree (your actual files and directories) remains unaffected.

##### Usage Example

Imagine accidentally committing a directory named `logs`. To untrack this directory without deleting the files locally, you would use:

```sh
git rm -r --cached logs
git commit -m "removing logs"
git push
```
--------