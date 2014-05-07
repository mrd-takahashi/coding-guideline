HTML
================

基本
---------------
+ HTMLバージョン ⇒ HTML5推奨
+ CSSレベル ⇒ CSS2.1〜
+ 文字コードト ⇒ UTF-8
+ 改行コード
  + LF(UNIX)
  + CR+LF(Windows)
+ タグ及び属性記述 ⇒ 小文字
+ 属性値の囲み ⇒ ダブルクォーテーション『"』
+ インデント ⇒ 半角スペース2個
+ 対応OS
  + PC ⇒ Windows,Mac
  + SP ⇒ Android,iOS
+ 対応ブラウザ(バージョン指定がないものは最新）
  + IE9〜
  + Chrome
  + Firefox
  + safari

**ただし、案件によりコーディング規約を指定された場合はこの限りではない。** 

ディレクトリ
---------------
ディレクトリ例  
![ディレクトリ例](http://www.m-r-design.com/images_outside/directory.png "ディレクトリ例")

ヘッダー
---------------
すべて記述する事は少ないが、記述順は下記の通り  

+ DOCTYPE宣言
+ charaset ⇒ 文字コード
+ title要素
+ meta要素 ⇒[参考](https://github.com/mrd-takahashi/coding-guideline/blob/master/META.md)
  + keywords
  + description
+ link要素
+ rel属性
  + stylecheet
  + shortcut icon(apple-touch-icon) ⇒[参考](https://github.com/mrd-takahashi/coding-guideline/blob/master/ETC.md)
  + canonical //URL正規タグ http://web-tan.forum.impressrd.jp/e/2009/03/05/5112
  + alternate //RSSフィードの指定
+ script要素
+ style要素
+ object要素
+ その他  

### タイトル要素   
指定がない場合は下記の内容で表示  

+ トップページ ⇒ 『サイト説明文 - サイト名』 または 『サイト名』
+ カテゴリートップ ⇒ 『カテゴリー名 | サイト説明文 - サイト名』 または 『カテゴリー名 | サイト名』
+ 個別ページ ⇒ 『ページ名 - カテゴリー名 | サイト説明文 - サイト名』 または 『ページ名 - カテゴリー名 | サイト名』
+ 文字数が60文字を超える場合は『ページ名(カテゴリー名) | サイト名』

### HTML5  
HTMLなのでXHTMLのように```<br />```などの終了タグ不要  
記述例 
```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>サイトタイトル</title>
    <meta name="keywords" content="hoge1,hoge2,hoge3">
    <meta name="description" content="hogehoge">
    <link rel="stylesheet" href="style.css">
    <link rel="shortcut icon" href="favicon.ico">
    <link rel="apple-touch-icon" href="apple-touch-icon.png"> //iOS/Androidショートカット用画像
    <link rel="canonical" href="http://~" > //URL正規タグ http://web-tan.forum.impressrd.jp/e/2009/03/05/5112
    <link rel="alternate" type="application/rss+xml" title="RSS" href="feed/"> //RSSフィードの指定
    <script src="/js/function.js"></script>
    <!--[if lt IE 9]>
      <script src="//html5shiv.googlecode.com/svn/trunk/html5.js"></script>
    <![endif]-->
  </head>
```


### HTML4  
HTMLなのでXHTMLのように```<br />```などの終了タグ不要  
記述例  
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <meta http-equiv="Content-Style-Type" content="text/css">
    <meta http-equiv="Content-Script-Type" content="text/javascript">
    <title>サイトタイトル</title>
    <meta name="keywords" content="hoge1,hoge2,hoge3">
    <meta name="description" content="hogehoge">
    <link type="text/css" rel="stylesheet" href="style.css">
    <link rel="shortcut icon" href="favicon.ico">
    <link rel="apple-touch-icon" href="apple-touch-icon.png"> //iOS/Androidショートカット用画像
    <link rel="canonical" href="http://~" > //URL正規タグ http://web-tan.forum.impressrd.jp/e/2009/03/05/5112
    <link rel="alternate" type="application/rss+xml" title="RSS" href="feed/"> //RSSフィードの指定
    <script type="text/javascript" src="/js/function.js"></script>
  </head>
```

パスの記述
---------------
サイト内のリンク・画像などはサイトルートパスで記述します。  
ただし、Wordpressのテーマ作成の場合は、CMSの性質上相対パスと絶対パスの混合になります。  
OK  ```<a href="/mypage/page.html">```  
NG  ```<a href="../mypage/page.html">```  

改行・インデント・コメント
---------------
改行とインデントを使って構造を判断しやすいように記述します。 

+ インデントは半角スペース2つ  
+ タブ文字はエディタによってサイズが変わるのでNG  
+ タブ文字と半角スペースを混在させる事もNG  
 
□は半角スペースを表します。 
また、```<div>``` の閉じ位置などがわかりづらい時に、タグを閉じた直後にコメントを入れます。
```html
<section>
□□<div id="profile">
□□□□<div class="profile-detail">
□□□□□□<div class="profile-img">
□□□□□□□□<img src="photo.jpg" height=100 width=100  alt="プロフィール画像">
□□□□□□</div>
□□□□□□<p>テキストテキストテキストテキストテキストテキスト<br>
□□□□□□テキストテキストテキストテキストテキストテキスト</p>
□□□□</div><!-- /.profile-detail -->
□□</div><!-- /#profile -->
</section>
```

*キーボードの[tab]を使い、効率よくインデントする方法*  
> DWの場合は設定を下記に変更する  
> [環境設定] ⇒ [コードフォーマット]  
> ⇒ 『インデント』チェック  
> ⇒  使用:2スペース  
> ⇒  タブサイズ2,『スペースとして挿入』チェック  


コーディング例
---------------
