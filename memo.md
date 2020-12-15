# git の使い方

githubにpush?するための方法を記す.


    $ git config --global user.name "username"
    $ git config --global user.email mail@address

で設定に名前とアドレスを追加できる.

    $ git config --list
で設定が確認可能.

    $git branch
    * main
とブランチが確認可能.

新規ファイルはコミットする前に`add`する必要がある.

    $git add memo.md

変更したら`commit`する.  

    $git commit -a

`-a`オプションはすべての修正をコミットするものである.