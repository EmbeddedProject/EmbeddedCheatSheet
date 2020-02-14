GIT:
====

## Starting point
## Show and Search
### View a file in a different git branch without changing branches
> git show branch:file
### Show all files changed between two commits:
> git log --name-only --pretty=oneline --full-index HEAD^^..HEAD | grep -vE '^[0-9a-f]{40} ' | sort | uniq
## Rename, Remove and Undo
### Rename a local and remote branch in git
> git branch -m new-name
> git push origin :old-name new-name
> git push origin -u new-name
### Revert all local changes to a branch and get back to the latest commit
> git reset --hard HEAD
## Commit and Archive
### Archive in tar.xz a repo
> git config tar.tar.xz.command "xz -c"
> git archive -o latest.zip HEAD
## Patch and apply patch
### Make numbered patch series between 2 commits
> git format-patch ee8ab42a74bd82006100e549bda4105f279024c7..HEAD






### Keep branch b up to date with branch a (works if branch b is a remote branch)
git checkout b
git merge a

### Keep branch b up to date with branch a (works if branch b is a local only branch)
git checkout b
git rebase a

### Create a remote git branch
git checkout -b <local-branch-name>
git push --set-upstream origin <local-branch-name>

### Default way to push changes to remote repo
git add <dateiname>
git commit -m "Commit text"
git push origin master

### Rebase changes from master to branch
git checkout branch
git rebase master
git mergetool --tool=meld
git rebase --continue

### Merge changes from master to branch
git checkout branch
git merge master

### Resolve merge conflicts
git mergetool --tool=meld

### show all branches
git branch -a

### stash the changes in a dirty working directory away
git stash

### create new branch, push the current branch and set the remote as upstream
git checkout -b [name_of_your_new_branch]
git push --set-upstream origin [name_of_your_new_branch]

### cherry pick commit from remote repo
git remote add other https:### example.link/repository.git
git fetch other
git cherry-pick <commit>

### cherry pick commit from remote repo
git --git-dir=../<some_other_repo>/.git format-patch -k -1 --stdout <commit SHA> | git am -3 -k

### generate a git patch for a specific commit
git format-patch -1 <sha>

### generate a git patchset from commit to commit
git format-patch -M 8208250eecda2e376b3aeabe6d453e549aa85ef2..419ad840c5c944c41be9e0793a424cc152ec13bf

### send git patch for specific commit
git send-email -1 <sha> --annotate

### send git patch version 2 for specific commit
git send-email -1 <sha> --annotate -v2

### send git patch for last 6 commits with a cover letter in [PATCH 0/6]
git send-email -6 --cover-letter --annotate

### undo git add
git reset <file>

### how to undo the last commit
git reset HEAD^

### show full diff combined with log
git log --full-diff -p [PATH]

### create numbered patch series from commit hash or tag to current HEAD
git format-patch -o [DIR] c2f321126e31cd69365e65ecd4a7c774e4fc71d2..HEAD
git format-patch -o [DIR] v3.10.40..HEAD

### create remote branch
git checkout -b <branch-name> # Create a new branch and check it out
git push -u <remote-name> <branch-name> # Push changes on branch to remote (origin)

### apply single patch
git apply file.patch

### apply multiple patches
git am *.patch

### show changes that have been staged
git diff --staged

### loop through subdirs containing .git and update them to current status
find . -iname ".git" -exec bash -c "cd '{}' && cd .. && git pull origin master" \;

### go back to commit git show c2f321126e31cd69365e65ecd4a7c774e4fc71d2 and create a temporary branch from this point on
git checkout -b tmp c2f321126e31cd69365e65ecd4a7c774e4fc71d2

### show commit
git show c2f321126e31cd69365e65ecd4a7c774e4fc71d2

### revert commit
git revert c2f321126e31cd69365e65ecd4a7c774e4fc71d2

### determine the URL that a local Git repository was originally cloned from
git config --get remote.origin.url
git remote show origin

### remove all local commits
git reset --hard origin/<branch_name>

### create archive from git branch
git archive --format=tar.gz -o ../<branch_name>.tar.gz <branch_name>

### create archive up to commit <SHA>
git archive --format=tar.gz -o ../<name>.tar.gz <SHA>

### show all tags
git tag

### list remotes for a git repository
git remote -v

