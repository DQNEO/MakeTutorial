# Makefileの書き方入門

# 目次
* Hello World
* カレーライスの作り方
* Makefileの書式

## Hello World


## カレーライスの作り方


## Makefileは依存関係を表現する

```
ターゲット名: 依存ファイル名 1 依存ファイル名 2 依存ファイル名 3
              コマンド行 1
              コマンド行 2
              コマンド行 3
```

```
hello: hello.c
       gcc -Wall -O2 -o hello hello.c
```
依存ファイル名のうちどれか一つでも更新されるとコマンドが実行される。

## 実行方法

`make ターゲット名`

ターゲット名を省略すると、Makefile内の一番先頭のターゲットを指定したのと同じになる。




## 参考

http://www.ie.u-ryukyu.ac.jp/~e085739/c.makefile.tuts.html "Makefile の書き方 (C 言語) — WTOPIA v1.0 documentation"
http://objectclub.jp/community/memorial/homepage3.nifty.com/masarl/article/gnu-make/rule.html "- 自動化のためのGNU Make入門講座 - Makefileの基本：ルール"
http://www.unixuser.org/~euske/doc/makefile/#terms "Make と Makefile の説明"
