
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

# ディレクトリ構成
##dist
コンパイル後のディレクトリ。
※コンパイルするためこのディレクトリはバージョン管理しない

##src
コンパイル用のファイルディレクトリ。
画像やpugなどはこちらをつかう。

###***src/assets***
SASS/images/js/font/など読み込むファイルはこのディレクトリにまとめる。

***src/assets/fonts***

WEBfontを格納
主に使用しているのは[NotoSans](https://www.google.com/get/noto/)
※日本語fontでなければCDNを使うのを推奨

***src/assets/js***

 汎用的なJSの関数を格納
 
***src/assets/scss***

SCSSを格納

***src/assets/scss/assets***
- _ggc_palette.scss
    - マテリアルカラーを変数化したファイル
    - 別に使わなくても良い
- _mixin.scss
    - 汎用的なMixin
    - 接頭語にcnt-を付けます
- _mixin_thme.scss
    - サイト独自のミックスイン
_ _extend
    - extendをまとめたもの
    - 接頭語にex-を付けます
- _variable
    - 設定値
- style
    - まとめのファイル

***src/assets/scss/assets/vendor***
外部で制作されたライブラリなどをまとめて置く場所※汎用的にいつも使うものを格納
個々のプロジェクト単位でディレクトリで区切る。

- [bourbon](http://neat.bourbon.io/)
    - MIXIN集

- [neat](http://neat.bourbon.io/)
    - GlidのMIXIN集

- [dlex](https://contiki9.github.io/dlex/)
    - FlexboxのCSSフレームワーク

- [skeleton](http://getskeleton.com/)
    - シンプルなレスポンシブ対応のフレームワーク。
    - 主にhtmlのみ見栄えとして活用
    
- [UIKIT](https://getuikit.com/)
    - なんでも揃ったCSSフレームワーク。
    - 接頭語に`uk-*`がつくのが特徴
     

***src/assets/images***

プロジェクトで共通して使う画像の格納場所

***src/assets/js***

プロジェクトで共通して使うJSの格納場所

---


## プロジェクト用CSS構成

[Atomic Parts Base CSS](http://apbcss.com/)に準ずる


以下は例外
### src/assets/scss/vendor

外部で制作されたライブラリなどをまとめて置く場所。
個々のプロジェクト単位でディレクトリで区切る。
```
//jqueryの場合

/jquery/jquery.js
```

### src/assets/scss/other

その他、どこにも属せない場合はここに管理


## Pugについて
pugはHTML生成のジェネレーターです。
PHPなどがなくてもコードの共通化が可能になるので積極的に使っていきます。

 - index.pug
    - TOPページの.pug。構成のサンプル用
 
### src/_include/c

- _layout.pug
    - ページの構成をまとめるベースの.pug

- _mixin.pug
    - .pugのMixin用ファイル
    
### src/_data/

サイト共通の情報を登録するjson

    
