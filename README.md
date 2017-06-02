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


# List branches (sorted by last modified)
  b = "!git for-each-ref --sort='-authordate' --format='%(authordate)%09%(objectname:short)%09%(refname)' refs/heads | sed -e 's-refs/heads/--'"


# Checkout to branch / Create branch
  co = checkout
  cob = checkout -b


# BE CAUTIOUS - Reset Hard
  rh = reset --hard HEAD


# List Aliases
  # For Windows
  # la = !git config --list | findstr "alias"
  # For Linux / Mac
  la = "!git config -l | grep alias | cut -c 7-"



# SETTINGS 

# Add colors
[color]
  ui = true
  diff = auto

# Avoid confusing merge commits with autorebase
[branch]
  autosetuprebase = always


```
