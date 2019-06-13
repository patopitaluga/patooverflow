# GIT Cheatsheet

Index:
* [Clear all your changes and start clean in sync with the last commit](#git-clean)


------

## <a name="git-clean"></a> Clear all your changes and start clean in sync with the last commit
-f means "force" and d means including folders
```
git stash
git clean -fd
```
git stash will keep the stash and will not remove untracked (new) files.

------
