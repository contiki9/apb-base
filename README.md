
# 概要
このリポジトリはwebサイトのテンプレートです。

Atomic Parts Base CSSの概念を元にアレンジを加えたものです。
http://apbcss.com/

まだ未完成で今後ルールが変わる可能性が高いですのでご注意ください。

# インストール
```
$ npm install 
```

```
$ gulp
```

## gulp コマンド

### ブラウザシンク

```
$ gulp sync 
```
コマンド後下記URLにアクセスしてください（意図的にブラウザが立ち上がらないようにしています）
http://localhost:3000/

### 納品データの作成
```
$ gulp build
```
### スタイルガイド作成

#### ただコンパイルする場合
```
$ gulp style
```

#### ブラウザシンク＆watch
編集する時用。

コマンド後下記URLにアクセスしてください（意図的にブラウザが立ち上がらないようにしています）
http://localhost:3000/
```
$ gulp guide
```
 
# ディレクトリ構成
##dist
コンパイル後のディレクトリ。
※コンパイルするためこのディレクトリは原則バージョン管理しない

##src
コンパイル用のファイルディレクトリ。
画像やpugなどはこちらをつかう。

###***src/assets***
scss/images/js/font/など読み込むファイルはこのディレクトリにまとめる。

***src/assets/fonts***

WEBfontを格納
主に使用しているのは[NotoSans](https://www.google.com/get/noto/)
※日本語fontでなければCDNを使うのを推奨

***src/assets/js***

汎用的なJSの関数を格納
 
***src/assets/scss***

SCSSを格納

***src/assets/images***

プロジェクトで共通して使う画像の格納場所

***src/assets/js***

プロジェクトで共通して使うJSの格納場所

---


## プロジェクト用CSS構成

### src/assets/scss/base
htmlの基本設定のファイルの置き場


### src/assets/scss/config

設定値などサイト全体で共通化して読み込むファイルの置き場

### src/assets/scss/pages

ページタイプ毎に使い分けるscssの置き場

基本的には`parts`のclassやラップ用のclass（`.w-*`）、レイアウト用のclass（`.l-*`）などの調整の範囲を限定する目的で使う。

原則接頭語に`.p-*`をつける

### src/assets/scss/parts

component集。

最小のcomponentには`.c-*`をつける。(cはcomponentの略です)
汎用性のあるcomponent群には`.b-*`を接頭語につける。(bはBlockの略です)

### src/assets/scss/vender

外部ライブラリーやフレームワークの置き場。

### src/assets/scss/other

その他、どこにも属せない場合はここに管理


## Pugについて
pugはHTML生成のジェネレーターです。
PHPなどがなくてもコードの共通化が可能になるので積極的に使っていきます。

 - index.pug
    - TOPページの.pug。構成のサンプル用
 
### src/_include/

- _layout.pug
    - ページの構成をまとめるベースの.pug

- _mixin.pug
    - .pugのMixin用ファイル
    
### src/_data/

サイト共通の情報を登録するjson

## CSSの名称ルール

まだ選定中。ころころ変わりそうですが基本概要は下記になります。

### .p-*
ページ単位でセレクターをスコープさせます。
原則body,またはbodyの直下に付けます。

そのタイプの下層ページには`--`を付けてからそのページの名称をいれます。
例)

`.p-home` 通常ページ用
`.p-home--category` 通常ページカテゴリの1階層目共通用
`.p-home-category--subcategory` 通常ページ特定のページ用

`.p-blog` ブログページ用
`.p-blog--search` ブログページの検索用
`.p-blog-single--postname` 特定の記事用

### .l-*

レイアウト用の名称です。
原則レイアウトはすべてflexboxを使います。

`.l-*`はあくまでレイアウトをつくるためのものなので、背景色や線のCSSを当てないでください。
基本、flexboxとmargenとpaddingのみです。（緩めの規約でOKです）


### .w-*

wrap用の名称です
原則、`.c-*``.b-*``.l-*`を囲います。
主に余白をつけるものです。


### .c-* .b-*

UIのパーツ群です。
使いまわす前提で作ります。

`.*-list-*`などモジュールの名前を必ず入れてください。
そのモジュール名毎のscssで管理します。

margenの値は入れないでください。paddingはOKです。
※margenを使う場合は必ず`.w-*`または別の`.b-*`に挟んで使ってください。


## CSSのlint 

SCSSのフォーマッターが走ります。

`npm run format`




    
