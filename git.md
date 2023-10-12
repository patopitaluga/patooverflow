# GIT Cheatsheet

Index:
* [Clear all your changes and start clean in sync with the last commit](#git-clean)
* [Delete local branch](#delete-local-branch)
* [Discard all changes in a single file](#discard-all-changesin-a-single-file)
* [List remotes of repository](#list-remotes-of-repository)
* ["Squash" multiple commits in a single commit to merge to parent branch](#git-squash)
* [Change last commit message](#commit-amend)
* [Add remote with credentials](#add-remote-with-credentials)
* [Setup upstream branch with the same name by default](#setup-upstream-branch-with-the-same-name)
* [Check current git user in terminal](#check-current-git-user-in-terminal)

------

## <a name="git-clean"></a> Clear all your changes and start clean in sync with the last commit
-f means "force" and d means including folders

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
git stash
git clean -fd
```
git stash will keep the stash and will not remove untracked (new) files.

------

## <a name="delete-local-branch"></a> Delete local branch

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
git branch -D branchname
```

------

## <a name="discard-all-changesin-a-single-file"></a> Discard all changes in a single file

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
git checkout {path-to-local-file}
```

------

## <a name="list-remotes-of-repository"></a> List remotes of repository
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
git remote -v
```

------

## <a name="git-squash"></a> "Squash" multiple commits in a single commit to merge to parent branch
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>

Chose a name for the new branch (usually your current branch + a sufix).
```
git checkout -b current-branch-name-with-sufix
git checkout target-branch-name
git merge --no-ff target-branch-name-with-sufix
git push origin target-branch-name
```

## <a name="commit-amend"></a> Change last commit message
```
git commit --amend -m "an updated commit message"
```

------

## <a name="add-remote-with-credentials"></a> Add remote with credentials

Sometimes when the repo and we are using different users to push to different repos is useful to set the remote origina as a url with credentials.

```
git remote set-url origin https://your-user:your-password@github.com/your-organization/your-repo.git
```

------

## <a name="setup-upstream-branch-with-the-same-name"></a> Setup upstream branch with the same name by default

To fix fatal: The current branch <MiBranch> has no upstream branch..

```
git config --global push.default current
```

------

## <a name="check-current-git-user-in-terminal"></a> Check current git user in terminal

```
git config --global --list --show-origin
```

------
Ignore the rest code. Is styling for local display of this file using https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
<style>
  .markdown-body {
    position: relative;
  }
  .cpy-btns {
    background: transparent;
    border: 0;
    cursor: pointer;
    display: block;
    font-family: monospace;
    font-size: 11px;
    margin-top: -4px;
    position: absolute;
    right: 45px;
    width: auto;
  }
  .cpy-btns::before {
    content: 'COPY'
  }
</style>
