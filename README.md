# Git Aliases Cheatsheet

## Important Concepts

#### Checking out to previous branch:
![Checking out to previous branch](https://i.imgur.com/QE6EPAs.jpg)


## Configure git to use proxy

```
git config --global http.proxy PROXY_URL:PORT


# or for specific domain:
git config --global http.https://domain.com.proxy PROXY_URL:PORT
git config --global http.https://domain.com.sslVerify false
```


## `.gitconfig` 

**Following aliases can be added to the `.gitconfig` present in your home directory:**

```
[alias]

# Oneline Log format
  ll = log --oneline

# Oneline Pretty Log Format
  l = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short

# Log (filtered by author) in the above format
  la = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short --author

# Log in Graphical / Ladder format
  lad = log --graph --decorate --name-status 
  # Optionally pass --all to view all branches

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

# Merge
  m = merge
  ma = merge --abort

# Show Config
  cf = config --list --local
  cfg = config --global -l
  cfa = config --list


# List branches (sorted by last modified)
  b = "!git for-each-ref --sort='-authordate' --format='%(authordate)%09%(objectname:short)%09%(refname)' refs/heads | sed -e 's-refs/heads/--'"
  br = branch -r # Remote branches only
  ba = branch -a # All branches (local and remote)
  
  
  # BE CAUTIOUS - Delete a local branch
  bd = branch -d # Politely ask git to delete a local branch
  bdf = branch -D # Forcibly delete a local branch

# Checkout to branch / Create branch
  co = checkout
  cob = checkout -b

# Checkout to previous branch
  cop = checkout - 
  # or alternatively:  
  # cop = checkout @{-1}

# git please =  --force-with-lease (checks your local copy of the ref is up-to-date before overwriting it)
  please = push --force-with-lease

# BE CAUTIOUS - Reset Hard
  rh = reset --hard HEAD

# BE CAUTIOUS - Clean untracked files and folders
  cc = clean -fd

# List Aliases
  # For Windows
  # a = !git config --list | findstr "alias"
  # For Linux / Mac
  a = "!git config -l | grep alias | cut -c 7-"

# Edit Config using default editor
  ec = config --global -e

# SETTINGS 

# Specify a global .gitignore
[core]
  excludesfile = ~/.gitignore
  
  # Set your default editor to
  # VS Code
  # editor = code --wait
  
  # Sublime Text 2/3:
	# editor = subl -w

  # Atom
	# editor = atom --wait


# Add colors
[color]
  ui = true
  diff = auto

# Avoid confusing merge commits with autorebase
[branch]
  autosetuprebase = always

# Push to the current branch by default
[push]
  default = current

# Remove usage hints
[advice]
  statusHints = false

# Show exact diff details instead of using a and b notation
[diff]
  mnemonicprefix = true


```


---

## CMDER Aliases

```cmd
;= @echo off
;= rem Call DOSKEY and use this file as the macrofile
;= %SystemRoot%\system32\doskey /listsize=1000 /macrofile=%0%
;= rem In batch mode, jump to the end of the file
;= goto:eof
;= Add aliases below here
e.=explorer .
gl=git log --oneline --all --graph --decorate  $*
ls=ls --show-control-chars -F --color $*
pwd=cd
clear=cls
history=cat "%CMDER_ROOT%\config\.history"
unalias=alias /d $1
vi=vim $*
cmderr=cd /d "%CMDER_ROOT%"

ll=ls -la
g=git $*
```
