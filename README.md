% タイトル
% 著者名
% 日付

# Author

ka

[![Gravatar](https://gravatar.com/avatar/884be098693425b409d25aaec5091de8?s=150)](https://gravatar.com/ka000)

Website: [kaosfield](http://www.kaosfield.net)

Twitter: [ka](https://twitter.com/ka_)

GitHub: [kaosf](https://github.com/kaosf)

# License

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-sa/4.0/)

Copyright (C) 2015 ka

# ヘッダ

文章

文章

# ヘッダ1

ヘッダ1で改ページ

## ヘッダ2

文章

### ヘッダ3

文章

# リスト順次表示

```md
- リスト順次表示1
- リスト順次表示2
- リスト順次表示3
```

- リスト順次表示1
- リスト順次表示2
- リスト順次表示3

# 順序付きリスト順次表示

```md
1. 順序付きリスト順次表示1
2. 順序付きリスト順次表示2
3. 順序付きリスト順次表示3
```

1. 順序付きリスト順次表示1
2. 順序付きリスト順次表示2
3. 順序付きリスト順次表示3

# リスト即時表示はHTMLタグ直書き

<ul>
<li>リスト即時表示1</li>
<li>リスト即時表示2</li>
<li>リスト即時表示3</li>
</ul>

<ol>
<li>順序付きリスト即時表示1</li>
<li>順序付きリスト即時表示2</li>
<li>順序付きリスト即時表示3</li>
</ol>

# HTMLソース

```html
<ul>
<li>リスト即時表示1</li>
<li>リスト即時表示2</li>
<li>リスト即時表示3</li>
</ul>

<ol>
<li>順序付きリスト即時表示1</li>
<li>順序付きリスト即時表示2</li>
<li>順序付きリスト即時表示3</li>
</ol>
```

この程度はさすがに面倒臭くはない

もしかしたらデフォルトの挙動を変える設定があるかも？

# ソースコード

C言語

```c
#include <stdio.h>

int main(int argc, char *argv[])
{
  printf("Hello, world!\n");
  return 0;
}
```

# ソースコード

Ruby

```ruby
def m
  puts 'Hello, world!'
end

m
```

# 引用文

```markdown
> これは引用文です
```

> これは引用文です

# 数式

$$1 + 2 = 3$$

When $a \ne 0$, there are two solutions to $ax^2 + bx + c = 0$ and they are

$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

$$f(a) = \frac{1}{2\pi i}\oint_C\frac{f(z)}{z-a}dz$$

$$f(x) = \sum^\infty_{n=0} \frac{f^{(n)}(a)}{n!}(x - a)^n$$

# 数式ソース

LaTeXで書ける

```
$$1 + 2 = 3$$

When $a \ne 0$, there are two solutions to $ax^2 + bx + c = 0$ and they are

$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

$$f(a) = \frac{1}{2\pi i}\oint_C\frac{f(z)}{z-a}dz$$

$$f(x) = \sum^\infty_{n=0} \frac{f^{(n)}(a)}{n!}(x - a)^n$$
```

# リスト順次表示と文章の混合

即時表示の文章は

- 後から
- こちらが
- 表示される

順次表示のリストの後にあっても即時表示される

#

ヘッダ1に何も書かない場合の文章の位置(ちょっと上にずれる)

# スライドの作り方

<ol>
<li>Pandoc, inotify-tools, [Slidy Builder](https://github.com/kaosf/slidy-builder), [Bash Watch](https://github.com/kaosf/bash-watch)をインストール</li>
<li>README.mdを用意する</li>
<li>以下のコマンドを走らせる
```sh
watchb 'slidybuild < README.md > index.html' 'index\.html'
```
</li>
<li>ブラウザでindex.htmlを開きREADME.mdを編集しつつ更新</li>
</ol>

README.mdに書いておけばGitHub上などでリポジトリのトップページに  
スライドの内容がざっと表示されることになるので便利そう．

# スライドの作り方(オフライン確認用)

オフラインで動作・見た目を確認を出来る状態にしたい場合

以下のコマンドを走らせる

```sh
watchb 'slidybuild -l < README.md > index.html' 'index\.html'
```

※先ほどと同様だがslidybuildコマンドに-lオプションを渡す

必要なJavaScript，CSS，PNGファイルが一度だけローカルにダウンロードされる

※MathJax.jsが176MBくらいあるので注意

生成されるindex.htmlもそれを使うようになる

# スライドの作られ方(1)

index.htmlの末尾にコメントとして

```sh
pandoc --version
```

の結果を再現性担保のために埋め込む

念の為その際に環境固有の情報を消すようにしてある

# スライドの作られ方(2)

index.htmlを生成するコマンドをinotifywaitコマンドで随時実行する

inotifywaitコマンドを生で使うのは大変なので補助ツールとして[Bash Watch](https://github.com/kaosf/bash-watch)を使う

# このスライドのリポジトリ

[kaosf/slidy-example](https://github.com/kaosf/slidy-example)

# おしまい
