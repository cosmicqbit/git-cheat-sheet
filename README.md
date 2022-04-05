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
