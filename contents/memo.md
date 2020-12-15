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

# markdown で書いたものをwebページに表示させる方法

静的なwebサイト？をmarkdown で書けるらしい.
要点は

* markdown で書ける
* css を当てられる.

cssにこだわらなければVScodeのプラグインでHTMLやPDFを吐き出せるそう.
場合によっては自身がwwwで作成する作業募とかは今後markdownで書くかもしれない.

[Marked](https://github.com/markedjs/marked)というJavaスクリプトライブラリを用いると markdown -> html変換を自動でしてくれるらしい.

~~~html
<!doctype html>
<html>
<head>
  <meta charset="utf-8"/>
  <title>Marked in the browser</title>
</head>
<body>
  <div id="content"></div>
  <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
  <script>
    document.getElementById('content').innerHTML =
      marked('# Marked in the browser\n\nRendered by **marked**.');
  </script>
</body>
</html>
~~~
だけでhtmlを変換できる……のか?