GIT SNIPPED:
============

### Show all files changed between two commits:
git log --name-only --pretty=oneline --full-index HEAD^^..HEAD | grep -vE '^[0-9a-f]{40} ' | sort | uniq

### Archive in tar.xz a repo
git config tar.tar.xz.command "xz -c"
git archive -o latest.zip HEAD

