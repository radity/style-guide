![Style guide](https://gokmengorgen.net/img/style-guide/code-part-pixelised.png "Style guide")

## EditorConfig
Please use [EditorConfig](https://editorconfig.org/) extension in your preferred IDE or editor. And copy the following config into **your project folder**:

```ini
# .editorconfig
root = true

[*]
charset = utf-8
end_of_line = lf
indent_size = 2
indent_style = space
insert_final_newline = true
trim_trailing_whitespace = true

[Makefile]
indent_style = tab

[*.cs]
indent_size = 4

[*.go]
indent_style = tab
indent_size = 8

[*.py]
indent_size = 4

[*.sh]
indent_size = 4
```

## Git config
We want to see your fullname and email correctly. Also it would be nice if you use gravatar to see your profile picture in your commits.

```ini
# ~/.gitconfig
[user]
    name = {{ YOUR FULLNAME }}
    email = {{ YOUR EMAIL }}
[alias]
    di = diff
    st = status -s
    ci = commit -v
    co = checkout
    br = branch
    prune-all = !git remote | xargs -n 1 git remote prune
    record = !git add -p && git ci
    amend-record = !git add -p && git ci --amend
    stoat = !toilet -f future STOATS
    update-master = !git checkout master && git pull -r
    lol = log --graph --decorate --pretty=oneline --abbrev-commit
    lola = log --graph --decorate --pretty=oneline --abbrev-commit --all
[color]
    branch = auto
    diff = auto
    interactive = auto
    status = auto
[core]
    autocrlf = false
    editor = nano
    whitespace = fix,-indent-with-non-tab,trailing-space,cr-at-eol
    excludesfile = ~/.gitignore_global
[filter "lfs"]
    clean = git-lfs clean -- %f
    smudge = git-lfs smudge -- %f
    process = git-lfs filter-process
    required = true
```

Please ignore IDE, editor, and OS specific files in **gitignore_global**:

```ini
# ~/.gitignore_global
.vscode
.idea
.vs

*.elc
.elisp/auto-complete
.elisp/magit
```
