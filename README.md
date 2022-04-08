# Git Cheat Sheet

## Table of Content
1. [Creating Snapshots](#Creating-Snapshots)
2. [Browsing History](#Browsing-History)
3. [Branching & Merging](#)
4. [Collaboration](#)
5. [Rewriting History](#)
## Creating Snapshots
**Initializing a repository**
```
git init
```

**Setting your Git credentials for every repository on your computer**
```
git config --global user.name "username"
git config --global user.email "email@example.com"
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

**Unstaging files (undoing git add)**
| Command | Description |
|:---------| :------------ |
|`git restore --staged file.css blob.js` | # Copies the last version of file from last snapshot to index

**Discarding local changes**
| Command | Description |
|:---------| :------------ |
|`git restore file.css` | # Copies file.css from index to working directory |
|`git restore file.css text.sh` | # Restore multiple files in working directory |
|`git restore .` | # Discards all local changes (except untracked files) |
|`git clean -fd` | # Removes all untracked files | 

**Restoring an earlier version of a file**
```
git restore --source=HEAD~2 file.js
```
---

## Browsing History

**Viewing the history**
| Command | Description |
|:---------| :------------ |
|`git log --stat` | # Shows the list of modified files |
|`git log --patch` | # Shows the actual changes (patches) |

**Filtering the history**
| Command | Description |
|:---------| :------------ |
|`git log -3` | # Shows the last 3 entries | 
|`git log --author="cosmicqbit"` | # Filter commits by author |
|`git log --before="2022-03-6"` | # Show commits before date |
|`git log --after="one week ago"` | # Show commits after date | 
|`git log --grep="GUI"` | # Commits with "GUI" in their message |
|`git log -S"Copy Tools"` | # Commits with "Copy Tools" in their patches |
|`git log hash1..hash2` | # Range of commits |
|`git log file.txt` | #Commits that touched file.txt |
