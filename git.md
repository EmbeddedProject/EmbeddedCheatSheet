GIT SNIPPED:
------------

# Show all files changed between two commits:
git log --name-only --pretty=oneline --full-index HEAD^^..HEAD | grep -vE '^[0-9a-f]{40} ' | sort | uniq

