# Private note
private note


## How to use github


### basic usage

```bash
$ git status
$ git add .
$ git commit -m "Something comment..."
$ git push origin master
```


### branch

```bash
$ git branch
$ git branch develop
$ git checkout develop
```


### merge

```bash
$ git checkout master
$ git merge develop
$ git push origin master
```


### add

```bash
$ git add file.py #対象ファイル
$ git add folder #フォルダ
$ git add folder1 folder2 #複数フォルダ
$ git add *.py #py拡張子全て
$ git add -A #更新ファイル全て
```

### commit message

```bash
$ git commit -F- <<EOF
> Some title
> 
> Problem: something
> Solve: something
```

### reset

```bash
$ git reset --hard HEAD^ #コミットを取り消しワークディレクトリも元に戻す
$ git reset --soft HEAD^ #コミットを取り消しワークディレクトリの内容はそのまま
$ git commit --amend -m "Something comment..." #コミットの上書き
$ git push -f origin master
```

```bash
$ git push -f origin HEAD^:master
$ git reset --soft HEAD^
$ # Fix a mistake
$ git add something
$ git commit -m "some comment"
$ git push origin master
```


### revert

```bash
$ git revert f33a2bc -n #-nはコメント編集なし. -eコメント編集あり
$ git push -f origin master
```


### add remote

```bash
$ git init
$ git remote add origin https://github.com/userid/yourproject.git
$ git add .
$ git commit -m "First commit"
$ git push -f origin master
```


### pull and fetch

```bash
$ git branch
feature
develop
master
[develop] $ git pull # Update develop branch. fetch and merge on develop branch
[master] $ # master branch is only fetched
[master] $ git merge origin/master
```


### following repository

```bash
$ git clone https://github.com/user/project
$ cd project
$ git branch -a
$ git remote add upstream https://github.com/author/project # Get from original project
$ git fetch upstream
$ git merge upstream/master
```


### get git log

```bash
# add your .bashrc
alias gitlog='git log --date=short --no-merges --pretty=format:"%cd %s %h (@%cn) "'
```


### .gitconfig

```bash
    ammend = "!f () { git commit --ammend -m \"$1 ($default)\" $2;}; f"
    cm = "!f () { git commit -m \"$1\" $2;}; f"
```


### diff log

```bash
#!/bin/sh

AUTHOR="bluelief"

LINES=$(git log --all --numstat --pretty="%H" --author="${AUTHOR}" --since="midnight" | awk 'NF==3 {plus+=$1; minus+=$2} END {printf("+%d, -%d\n", plus, minus)}')

MESSAGE="[insertions, deletions]: \\n ${LINES}\\n"

printf "${MESSAGE}"
```

`git log --all --numstat --pretty="%H" --author="bluelief" --since="" --until="" | awk 'NF==3 {plus+=$1; minus+=$2} END {printf("+%d, -%d\n", plus, minus)}'`


### git branch on terminal

```bash
function parse_git_branch {
    git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ [\1]/'
}

# Tested on Ubuntu
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\e[1;32m\]$(parse_git_branch)\[\033[00m\]\$ '
```


# h1 size

## h2 size

### h3 size

#### h4 size

##### h5 size

*strong*strong  
**strong**strong  

> quote  
> quote

- [ ] checklist1
- [x] checklist2

* 1
* 2
* 3

- 1
- 2
- 3
