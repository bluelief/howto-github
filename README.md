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

### reset

```bash
$ git reset --hard HEAD^ #コミットを取り消しワークディレクトリも元に戻す
$ git reset --soft HEAD^ #コミットを取り消しワークディレクトリの内容はそのまま
$ git commit --amend -m "Something comment..." #コミットの上書き
$ git push -f origin master
```

### revert

```bash
$ git revert f33a2bc -n #-nはコメント編集なし. -eコメント編集あり
$ git push -f origin master
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
