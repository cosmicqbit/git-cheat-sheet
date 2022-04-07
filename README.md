# Git Cheat Sheet
      
## Creating Snapshots
**Initializing a repository**
```
git init
```

**Staging files**
| Command | Description |
|:---------| :------------ |
|`git add file1.js` | # Stages a single file |
|`git add file.js file2.js` | # Stages multiple files |
|`git add *.js` | # Stages with a pattern |
|`git add .` | # Stages the current directory and all its content |

**Viewing the status**
| Command | Description |
|:---------| :------------ |
|`git status` | # Full status |
|`git status -s` | # Short status |


**Committing the staged files**
| Command | Description |
|:---------| :------------ |
|`git commit -m "Message"` | # Commits with a one-line message |
|`git commit` | # Opens the default editor to type a long message |

**Removing files**
| Command | Description |
|:---------| :------------ |
|`git rm file1.js` | # Removes from working directory & staging area |
|`git rm --cached file1.js` | # Removes fom staging area only |

**Renaming or moving files**
| Command | Description |
|:---------| :------------ |
|`git mv file.js file1.js`| # Renames or moves existing file to new |


**Viewing the staged/unstaged changes**
| Command | Description |
|:---------| :------------ |
|`git diff` | # Shows unstaged changes |
|`git diff --staged`| # Shows staged changes |
|`git diff --cached` | # Same as the above |

**Viewing the history**
| Command | Description |
|:---------| :------------ |
|`git log` | # Full history |
|`git log --oneline` | # Summary |
|`git log --reverse` | # Lists the commits from the oldest to the newest |

**Viewing a commit**
| Command | Description |
|:---------| :------------ |
|`git show 93412ff` | # Shows the given commit |
|`git show HEAD` | # Shows the last commit |
|`git show HEAD~2` | # Two steps before the last commmit |
|`git show HEAD:file.js` | # Shows the version of file.js store in the last commit |
|`git ls-tree HEAD~1` | # Shows commit when multiple directorires are included |
