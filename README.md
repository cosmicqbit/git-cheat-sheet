# Git Cheat Sheet

## Table of Content
1. [Creating Snapshots](#Creating-Snapshots)
2. [Browsing History](#Browsing-History)
3. [Branching & Merging](#Branching--Merging)
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

**Formatting the log output**
| Command | Description |
|:---------| :------------ |
|`git log --pretty=format:"%an commited %H"` | # Shows author name commited hash |
`git log --pretty=format:"%an commited %h on %cd "` | # Above with commit date |
`git log --pretty=format:"%Cgreen%an%Creset commited %H"` | # Colorizes the author name | 

**Creating an alias**
| Command | Description |
|:---------| :------------ |
|`git config --global alias.lg "log --oneline"` | # `git lg` will do the job |
|`git config --global alias.unstage "restore --staged` | # `git unstage` will do the job |

**Viewing a commit**
| Command | Description |
|:---------| :------------ |
|`git show HEAD~2` | # Alt method for displaying using hash |
|`git show HEAD~2 HEAD file.txt` | # Changes to file.txt only | 

**Comparing commits**
| Command | Description |
|:---------| :------------ |
|`git diff HEAD~2 HEAD` | # Shows the changes between two commits |
|`git diff HEAD~2 HEAD file.txt` | # Changes to file.txt only |


**Checking out a commits**
| Command | Description |
|:---------| :------------ |
|`git checkout rad763g` | # Checks out the given commit |
|`git checkout master` | # Checks out the master branch | 

**Finding a bad commit (Bisection method)**
| Command | Description |
|:---------| :------------ |
|`git bisect start`| # Initializing the method |
|`git bisect bad` | # Marks the current commit as a bad commit |
|`git bisect good ca49190` | # Marks the given commit as a good commit |
|`git bisect reset` | # Terminates the bisect session |

**Finding contributors**
| Command | Description |
|:---------| :------------ |
|`git shortlog` | # List contributors list |
|`git shortlog -n -s -e` | # Lists contributors in order, suppresses commit m & displays email |   

**Viewing the history of a file**
| Command | Description |
|:---------| :------------ |
|`git log file.txt` | # Shows the commits that touched file.txt |
|`git log --oneline --stat file.txt` | # Shows stats (no of changes) for file.txt |
|`git log --patch file.txt` | # Shows the patches (changes) applied to file.txt | 
  
**Recovering a deleted file**
| Command | Description |
|:---------| :------------ |
|`git log --oneline -- toc.txt` | # List all commits which touched the file |
|`git checkout a64d33 toc.txt` |# Step 2 |
|`git status -s` |# Step 3|
|`git commit -m "commit message"` |# Step 4 |

**Finding the author of line(s)**
| Command | Description |
|:---------| :------------ |
|`git blame file.txt` | # Shows the author of each line in file.txt | 

**Tagging**
| Command | Description |
|:---------| :------------ |
|`git tag v1.0` | # Tags the last commit  as v1.0 |
|`git tag v.1.0.1 4e4a897` | # Tags an earlier commit |
|`git checkout v.1.9` | # Checks out the given tag |
|`git tag` | # Lists all the tags |
|`git tag -a v1.1 -m "My version 1.1"` | # Create annotated tag |
|`git tag -n` | # Display commit messages with annotated tags |
|`git show v1.1` | # Show tag details |
|`git tag -d v1.1` | # Deletes the given tag

## Branching & Merging
---

**Managing branches**
| Command | Description |
|:---------| :------------ |
|`git branch bugfix` | # Creates a new branch called bugfix |
|`git checkout feature` | # Switches to the feature branch |
|`git switch feature` | # Same as the above |
