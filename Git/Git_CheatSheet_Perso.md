# Git

### Take a previous version of a file
```bash
git checkout <commit_id> <file/to/restore>
```

### Partial commit of a file
```
git add --patch file
git add -p file
# During selection of part, press ? for displaying the help
```

### Show old version of file
```
git show  HEAD~:path/to/file
git show  HEAD~:path/to/file | vim - # With vim
```

### Print commit history only on some files
```
git log -- /path/file1 /path/file1 /path/directory1
```

### Print Hash of last commit
```
git log -n 1 --pretty=format:"%H"
```

### Get git root directory
```
git rev-parse --show-toplevel
```

### Force pushing change after a first push
1. Soft method: (will be abort if already new commit)
```
git push --force-with-lease <repository> <branch>
git push <repository> +<branch>
```
2. Hard one:
```
git push --force <repository> <branch>
```

### Clean repository, remove untracked files
```
git clean -dn
```

### Apply commit from other forks

#### Method 
1. Add the other fork as a remote of your repo:
```
git remote add otherfork git://github.com/request-author/project.git
```
2. Fetch his repo's commits
```
git fetch otherfork
```
3. You have then two options to apply the pull request (if you don't want to choose pick 1.)

##### Follow last PR commit


If you don't care about applying also the eventual commits that have been added between the origin and the pull request, you can just rebase the branch on which the pull request was formed.

```
git rebase master otherfork/pullrequest-branch
```

##### Add those PR commits to your commits


If you only want the commits in the pull request, identify their SHA1 and do
```
git cherry-pick <first-SHA1> <second-SHA1> <etc.>
```

#### Method alternative
1. git pull <URL_fork> <branch_fork>
2. Merge <branch_fork> to actual working branch

### How do I push amended commit to the remote Git repository?

Tip to recover from the situation after you have pushed out the amended commit with --force (or +master).

Find the old commit that you amended (call it old, and we'll call the new commit you created by amending new).
Create a merge between old and new, recording the tree of new, like git checkout new && git merge -s ours old.
Merge that to your master with git merge master
Update your master with the result with git push . HEAD:master
Push the result out.

Then people who were unfortunate enough to have based their work on the commit you obliterated by amending and forcing a push (which is you're being a very very bad boy) will see the resulting merge will see that you favor new over old. Their later merges will not see the conflicts between old and new that resulted from your amending, so they do not have to suffer.
