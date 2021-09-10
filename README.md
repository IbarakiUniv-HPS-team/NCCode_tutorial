# NC-Code_tutorial
NC Codeのコード作成チュートリアル


## Gitを使った共同開発を経験しよう(2021.09.02)

####  このレポジトリをローカルにcloneしよう

```git
$ git clone https://github.com/IbarakiUniv-HPS-team/NCCode_tutorial.git
```

#### branchを切ろう．(branch名は苗字のローマ字表記にしよう)

```git
$ git status
>> On branch main
   Your branch is up to date with 'origin/main'.

$ git branch
>> *main

$ git branch dev01 //dev01 はブランチの名前

$ git branch
>> *main
    dev01

$ git switch dev01
>> Switched to branch 'dev01'

$ git switch -c dev01 // git branch と git switch を同時に行う

$ git branch
>> *dev01
    main
```


#### branchで編集しよう
branchがswitchされているか確認しよう．
```git
$ git branch
>> *dev01
    main
```

`main.cpp`に以下を追加しよう．

```cpp
cout << "dev01 で編集" << endl;
```

#### branchをpushしてGitHubにbranchを追加しよう

```git
$ git push --set-upstream origin dev01 //branchをpush
>> remote:
remote: Create a pull request for 'dev01' on GitHub by visiting:
remote:      https://github.com/IbarakiUniv-HPS-team/NCCode_tutorial/pull/new/dev01
remote:
To https://github.com/IbarakiUniv-HPS-team/NCCode_tutorial.git
 * [new branch]      dev01 -> dev01
Branch 'dev01' set up to track remote branch 'dev01' from 'origin'.
```

#### 編集したファイルをpushしよう

```git
$ git status
>> On branch dev01
Your branch is up to date with 'origin/dev01'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md <- 変更が反映されていないファイルが表示される

no changes added to commit (use "git add" and/or "git commit -a")
$ git add main.cpp
$ git commit -m "変更した内容を書く"
$ git push origin dev01
```

#### プルリクエストを作成しよう
ここまで実行した後にGitHubの該当するレポジトリに行くと `pull request` ができるようになっているはず．このときに `code review`を自分以外の開発者に依頼する．

#### Merge する
プルリクエストの内容で問題なければ開発責任者がMergeをする．ここでbranchの内容がmainに反映される．

#### branchにmainの内容を反映させる

```git
$ git switch main
$ git pull origin main
$ git switch dev01
$ git merge main //ここまでやると反映される？
($ git push origin test)
```




