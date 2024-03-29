# Useful GIT


------------
### Command List

- [git rm -r --cached (remove file from remote only)](#Remove-file-from-remote-only)
- [git bisect find a commit that indtroduced a bug](#Find-a-commit-that-introduced-a-bug)

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
 

---


####  Find a commit that introduced a bug
#### `git bisect` 

The `git bisect` command is a powerful tool for debugging and finding the commit that introduced a bug or regression in your codebase. It performs a binary search through your commit history to help you identify the problematic commit efficiently.

Provide a known "bad" commit where the issue is present and a known "good" commit where the issue does not exist. Git will then automatically checkout commits in between these two points and allow you to test each one. 

Based on your feedback (marking a commit as "good" or "bad"), Git narrows down the search until it finds the first commit that introduced the problem.

Example usage:
```
$ git bisect start
$ git bisect bad <bad_commit>
$ git bisect good <good_commit>
```

Git will then checkout a commit in the middle for you to test. After testing, mark the commit as "good" or "bad" using `git bisect good` or `git bisect bad`, respectively. Continue this process until Git identifies the problematic commit.

---