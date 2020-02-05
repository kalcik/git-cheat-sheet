## Git Configuration
|<span>||
|:---|:---|
|```git config --global alias.[alias name] "[command]"```|Add alias for command <br>Examples: <br> ```git config --global alias.co checkout``` <br>  ```git config --global alias.ac "!func() { git add -u; git commit -m \"${1}\"; }; func" ```|
|```git config --global core.editor "[path to editor]"```|Set global editor|
|```git config --global credential.helper "[path to credential helper]"```|Set global credential helper|
|```git config --global -e```|Edit global configuration <br> Example to set Visual Studio Code as a diff editor: <br> ```[diff]``` <br> ```tool = default-difftool``` <br> ```[difftool "default-difftool"]``` <br> ```cmd = [code --wait --diff $LOCAL $REMOTE ]```|
|```git config --list --show-origin```|Show all git config files|

## Create a Repository
|<span>||
|:---|:---|
|```git clone [project url]```|Clone from an existing repository|
|```git init [project name]```|Create a new local repository|

## Make a change
|<span>||
|:---|:---|
|```git add .```|Mark only new and modified as staged|  
|```git add -A```|Mark all (untracked, new, modified and changed) files as staged|
|```git add -u```|Mark only tracked changed files as staged|
|```git commit -am"[commit message]"```|Commit all tracked files with a message|
|```git commit -m"[commit message]"```|Commit changes|
|```git cherry-pick [commit id]```|Apply specific change identified by commit id on current branch|
|```git rebase --continue```|Continue rebase after resolve merge confict(s)|
|```git stash```|Stash current changes for later|
|```git stash apply```|Apply latest stashed change|
|```git stash drop```|Delete lastest change from stash list|
|```git stash drop [stash number]```|Delete change with specific number from stash list|
|```git stash list```|Show list of stashed changes|
|```git tag [tag name]```|Create a tag on latest commit|
|```git tag -a [tag name]```|Add tag with a message|
|```git commit --amend -m"[Message]"``` <br> ```git push --force-with-lease```|Change last commit message|

## Undone a change
|<span>||
|:---|:---|
|```git reset --soft HEAD~1```|Reset changes from HEAD to penultimate commit, last commit is undone and staged|
|```git reset --mixed HEAD~1```|Reset changes from HEAD to penultimate commit, last commit changes are visible but _not_ staged|
|```git reset --hard HEAD~1```|Reset changes from HEAD to penultimate commit, last commit are _not_ visible|
|```git reset --hard origin\[branch name]```|Reset local changes from HEAD to last remote commit|
|```git checkout HEAD [file]```|Undo specific file to last commit|
|```git clean -d -f```|Clean all local changes|

## Synchronize
|<span>||
|:---|:---|
|```git fetch```|Get remote changes from origin but without merge|
|```git fetch --prune```|Refresh remote branches|
|```git push```|Push staged changes to origin repository|
|```git push origin +HEAD```|Push local HEAD over the remote HEAD|
|```git push --tags```|Push tags|
|```git pull```|Fetch and merge from origin|
|```git pull --rebase```|Fetch, merge and rebase latest changes from origin|

## Observe a Repository
|<span>||
|:---|:---|
|```git blame [file]```|Show differences between the first and second commit id|
|```git diff HEAD```|Show all staged and unstaged file changes|
|```git diff --cached```|Show changes between staged files and repository|
|```git diff [commit id]..[commit id]```|Show differences between the first and second commit id|
|```git log -u [filename]```|Show all commits related to files|
|```git log -p [file/directory]```|Show change history for file/directory including diffs
|```git log --all --decorate --oneline --graph --simplify-by-decoration```|Show only relationship between commits by graph|
|```git log --oneline```|Show log with only one message per line|
|```git log --oneline --graph```|Show log as graph|
|```git log --oneline --graph --all --decorate```|Show log as graph for all branches decorated by tags, HEAD, source and target branch|
|```git log [source branch]..[branch to see changes on] --oneline```|Show log only for specific branch|
|```git shortlog```|Show shortlog (with name of commiter)|
|```git shortlog -sne```|Show shortlog as a numbered summary with emails of commiters|
|```git show [commit id]:[file]```|Show the file changes for a commit id and/or file
|```git status```|Show status of changes|

## Working with Branches
|<span>||
|:---|:---|
|```git branch -av```|List all branches, local and remote|
|```git branch [branch name]```|Create branch|
|```git branch -m [new branch name]```|Rename local branch|
|```git branch -d [branch name]```|Delete local branch|
|```git branch -D [branch name]```|Force to delete local branch (event if not pushed to the remote)|
|```git branch [branch name] [commit id]```|Create branch based on specific commit|
|```git checkout [branch name]```|Switch to branch|
|```git checkout -b [branch name]```|Create and checkout the created branch|
|```git merge [branch name from merge to]```|Merge specific branch into current branch|
|```git push origin [branch name]```|Create new remote branch|
|```git push origin --delete feature/new-feature```|Delete the remote branch|
|```git rebase [target branch]``` <br> ```git checkout [master]``` <br> ```git merge [source branch]```|Relocate change from source branch on target branch|
|```git reflog``` <br> ```git [branch name] [id of reference taken from reflog]```|Recreate local deleted branch|
|```git stash branch [branch name]```|Create new branch and apply latest stashed change|
|```git stash branch [branch name] [stash number]```|Create new branch and apply stashed change with specific number|
|```git --set-upstream [local branch name] origin/[remote branch name]```|Setup connection between local and remote branch|
|```git --set-upstream origin [remote branch name]```|Setup connection between current and remote branch|

## Help
|<span>||
|:---|:---|
|```git command --help```|Git help on specific command|
