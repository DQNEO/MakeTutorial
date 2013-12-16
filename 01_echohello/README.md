## Hello World

### いきなりですがmakeしてみましょう

なにはなくとも、まずmakeしてみましょう。
```
mkdir sample1
cd sampl1
make
```

はい、エラーが出ました。
```
make: *** ターゲットが指定されておらず, makefile も見つかりません.  中止.
```

当然ですね。
ここには２つのエラーが書かれています。
1. ターゲットが指定されていない
2. makefileが存在しない

### Makefileを作ってみる

では空のMakefileを作ってみましょう。
```
touch Makefile
make
```

```
make: *** ターゲットがありません.  中止.
```

おー、エラーが一個減りました。

### ターゲットを書く

ターゲットというのは「タスク」だと思ってください。
Makefileを編集して、このように書いてみてください。
```
hello:

```

ターゲット"hello"を定義しました。
中身は空なのでこのターゲットは何の仕事もしません。

では実行してみましょう。

```
make hello
make: `hello' に対して行うべき事はありません.
```

タスクの中身が定義されてないので当然の結果ですね。

ではタスクの中身を書いてみましょう。
タスクは、ターゲット行の次の行に、タブコードに続けてコマンドを書きます。

```
hello:
	echo hello world
```

実行してみましょう。

```
$ make hello
echo hello world
hello world
```

ターゲットhelloが実行されました！

おめでとうございます。

ちなみに、makeを実行するときのターゲット名(hello)は省略することができます。
単にmakeとのみ打った場合、Makefile内で一番最初に書かれているターゲットを指定したのと同じになります。

```
$ make hello
echo hello world
hello world
```

このように、makeとはコマンドを書いて実行するための仕組みです。
shellscriptと同じようなものですね。

## 成果物を作らせる
さてmakeは普通、何らかの成果物(ファイル)を作るために実行します。

makeにファイル作成をさせてみましょう。

```
hello:
	echo hello world > hello
```

実行します。
```
$ make
echo hello world > hello
```

hello ファイルが作成されました。

## ゴミ掃除

生成されたファイルを削除する仕事もmakeにやらせてみましょう。
ターゲットhelloにつづいてターゲットcleanを定義します。
```
hello:
	echo hello world > hello

clean:
	rm hello
```

実行します。
```
$ make clean
rm hello
```
するとファイルhelloが削除されます。

### まとめ
ターゲットhelloとcleanを定義してmakeに仕事をさせることができました。
makeとは、第一義的に「タスク」を定義して実行させるための仕組みである、ということがわかりましたね。

