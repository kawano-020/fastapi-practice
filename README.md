# fastapi-practice

開発環境の構築とContainer間の通信まで

---

# 環境構築

## Gitの設定

誤ってmainブランチにcommitしないように、開発を開始する前に次のコマンドを実行してください。

この操作は1回で十分ですが、開発環境などを変更した場合は、再度同じ操作を行う必要があります。

```
$ git config --local core.hooksPath .githooks
```

このスクリプトが正常に構成されているかどうかは、次のコマンドで確認できます。

```
$ git commit --allow-empty -m "test commit"
```

以下のようなエラーがraiseされたら設定完了です。

```
Error: Attempt to commit to main branch.
If you want to commit new changes, you can create a new branch, checkout, and commit using:
  git checkout -b new_branch
  git commit -m 'What did you change?'
```

#### ※ 以下のようなメッセージが出た場合の対処

```
hint: The '.githooks/pre-commit' hook was ignored because it's not set as executable.
hint: You can disable this warning with `git config advice.ignoredHook false`.

```

`.githooks/pre-commit`に対する実行権限を与えてください。

```
$ chmod +x .githooks/pre-commit
```

#### ※ pre-commitスクリプトを無視したい場合
* commitコマンド実行時に`--no-verify`とすることで無視できます。
  * `git commit --no-verify ...`

#### DOTO: 各項目のinstallation・使用方法を書く
* docker-compose (container manager)
* poetry (package manager)
* pysen (linter)
