# Git Aliases Cheatsheet


#### Following aliases can be added to `.gitconfig` in your home directory: 

```
[alias]

# Oneline Log format
  ll = log --oneline

# Oneline Pretty Log Format
  l = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short

# Status
  s = status
  st = status -s

# Add Files to staging
  a = add
  ap = add -p

# Diff changes
  d = diff
  ds = diff --stat
  dc = diff --cached

# Commit staged files
  c = commit --verbose
  ca = commit -a --verbose
  cm = commit -m
  cam = commit -a -m
  m = commit --amend --verbose

```
