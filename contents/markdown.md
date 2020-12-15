# マークダウンことはじめ
Vscode でマークダウンのプレビューをするためには[Ctrl] + [K]でコマンドモードにしてから[V]を押す.
記法サンプルは https://qiita.com/tbpgr/items/989c6badefff69377da7 を参考にした

# 見出し
1個から6個シャープで見出しをつける

    # 見出し1
    ## 見出し2
    ### 見出し3
    #### 見出し4
    ##### 見出し5
    ###### 見出し6

### 表示例
# 見出し1
## 見出し2
### 見出し3
#### 見出し4
##### 見出し5
###### 見出し6

# 箇条書き
ハイフン, プラス, アスタリスクとスペースでリストを作成できる.  
ネストはtabかスペース二つで作成可能

    - リスト(-)
        - ネスト(tab)
    + リスト(+)
      - ネスト(スペース二つ)
    * リスト1(*)
### 表示例
- リスト(-)
    - ネスト(tab)
+ リスト(+)
  - ネスト(スペース二つ)
* リスト1(*)

# 番号付きリスト
数値と半角ドットで番号付きリストを作成可能  
番号は何でもよい.  
こちらはtab出ないとネスト出来ない模様?

    1. 番号付きリスト  
        1. 番号付きリスト(tab)  
      1. 番号付きリスト(スペース二つ)  
    1. 番号付きリスト  

### 表示例
1. 番号付きリスト  
    1. 番号付きリスト(tab)  
  1. 番号付きリスト(スペース二つ)  
1. 番号付きリスト  

# 引用  
小なり記号で引用ができる

    > 引用文

### 表示例
> 引用文

## 二重引用

小なり記号を二つ重ねると二重引用できる  

    >番号付きリストはtabじゃないとネストできないらしいから注意  
    >
    >>リストを作成する際はスペース二つでネストできる  
    >>(番号付きもそうなのかな?)

### 表示例
>番号付きリストはtabじゃないとネストできないらしいから注意  
>
>>リストを作成する際はスペース二つでネストできる  
>>(番号付きもそうなのかな?)

# 改行
行末にスペースを二ついれると改行される.

    これが  
    テストdeth
    空白を入れないとこうなるよ

### 表示例
これが  
テストdeth
空白を入れないとこうなるよ


# pre記法
半角スペース4つもしくはtabでコードブロックをpre表示できる.

        # space
        #!/usr/bin/bash
        ls | grep hoge

    ---

        # tab
        #!/usr/bin/bash
        ls | grep hoge

### 表示例
    # space
    #!/usr/bin/bash
    ls | grep hoge

---

    # tab
    #!/usr/bin/bash
    ls | grep hoge

# code記法

バッククオートで文字列を囲むとコードの一部を表示可能

    パッケージをアップグレードするときは `apt upgrade` とコマンドを打ってね

### 表示例
パッケージをアップグレードするときは `apt upgrade` とコマンドを打ってね

# 強調: italic
アスタリスクもしくはアンダースコアで囲むと斜体になる

    normal *italic*  
    normal _italic_

### 表示例
normal *italic*  
normal _italic_

# 強調 bold

アスタリスクもしくはアンダースコア2つで囲むと太字になる

    normal **bold**  
    normal __bold__

### 表示例
normal **bold**  
normal __bold__

# 強調 italic + bold

アスタリスクもしくはアンダースコア2つで囲むと太字兼斜体になる

    normal ***bold***  
    normal ___italic___

### 表示例
normal ***bold***  
normal ___italic___

# 水平線
アンダースコア, アスタリスク, ハイフンなどを3つ以上連続して記述すると水平線が表示できる.
※連続するハイフンの間にはスペースがあってもよい.

    ___
    ***
    ---
    - - -

### 表示例
___
***
---
- - -

# リンク
`[表示文字](URL)`でリンクを表示できる.

    [今回の参考URL](https://qiita.com/tbpgr/items/989c6badefff69377da7)

### 表示例
[今回の参考URL](https://qiita.com/tbpgr/items/989c6badefff69377da7)

# 定義参照リンク
ってのがあるらしい.
Markdownの文書の途中に長いリンクを記述したくない場合は、  
同じリンクの参照を何度も利用する場合は、リンク先への参照を定義することができます。  
とのこと.
でも上手くいかない？

    [参考URL][今回の参考URL]

    なんかふざけたの

    [適当なURL][今回の参考URL]

### 表示例
[参考URL][今回の参考URL]

なんかふざけたの

[適当なURL][今回の参考URL]

# GitHub Flavored Markdown(GFM)
markdown に github の独自仕様を加えたmarkdown 記法
以降GFMと記す.

# GFM : リンク記法

URLを記述するだけでリンクになる

    https://www.google.co.jp

### 表示例
https://www.google.co.jp

# GFM: 取り消し線
チルダ2個で文字列を囲むと取り消し線を使える.

    ~~取り消し線~~

### 表示例
~~取り消し線~~

# GFM:pre記法(チルダ * 3, バッククオート * 3

    ~~~
    # チルダ
    #!/usr/bin/bash
    ls | grep hoge
    ~~~
    ```
    # バッククオート
    #!/usr/bin/bash
    ls | grep hoge
    ```

### 表示例
~~~
# チルダ
#!/usr/bin/bash
ls | grep hoge
~~~
```
# バッククオート
#!/usr/bin/bash
ls | grep hoge
```

# GFM: pre記法(シンタックスハイライト)

チルダ, もしくはバッククオート3つの後ろに対象シンタックスの言語を記述する.

    ~~~bash
    # チルダ
    #!/usr/bin/bash
    ls | grep hoge
    export hogehoge=herohero
    ~~~

### 表示例
~~~bash
# チルダ
#!/usr/bin/bash
ls | grep hoge
export hogehoge=herohero
~~~

# GFM:表組み

    |header1|header2|header3|
    |:--|:--:|--:|
    |align left|align center|align right|
    |a|b|c|

### 表示例
|header1|header2|header3|
|:--|:--:|--:|
|align left|align center|align right|
|a|b|c|

# GFM:ページ内リンク

GFMを利用すると見出し記法を利用した際にアンカーが張られ, それを利用してリンクが貼れる.

    ## menu
    * [to header1](#header1)
    * [to header2](#header2)

    <-- mochi mochi every day -->

    [return to menu](#menu)
    ### header1
    ### header2

### 表示例
## menu
* [to header1](#header1)
* [to header2](#header2)

<-- mochi mochi every day -->

[return to menu](#menu)
### header1
### header2

## 参考

最初にも記したが, 参考文献は以下である.

[Markdown記法 サンプル集](https://qiita.com/tbpgr/items/989c6badefff69377da7)