META
================
通常使用しないものも含まれる。

+ charaset ⇒文字コード
+ content ⇒メタデーターの値など
+ [name](#NAME)
  + authorm ⇒ 文章の作者
  + keywords ⇒ キーワード
  + description ⇒ サイト説明
  + robot ⇒ 検索エンジンクローラーへの指示(W3Cの仕様には記載なし)
  + application-name ⇒ HTML5追加要素ウェブアプリケーションのみ使用可
  + generator ⇒ 通常使用しない
+ [http-equiv](#HTTP-EQUIV)(プラグマ指示子。ブラウザに対して文章の状態・挙動を指示する役割）
  + default-style ⇒ デフォルトCSSの指定
  + refresh ⇒ リダイレクト・再読み込みの指定

<a name="NAME">name
---------------
**文章制作者**  
```html
<meta name="authorm" content="作者名">
```

**キーワード**  
たくさん指定しても意味がないので3~5程度。  
現在SEO対策として効果はない。  
出典:http://seo.siyo.org/engine/seo8625/
```html
<meta name="keywords" content="hoge1,hoge2,hoge3">
```

**サイト説明**  
検索結果に表示されるので文字数は50～100文字程度。それを超えると文字切りされてしまうので注意。

| 検索エンジン | 文字数 | 
|:-----|:-----|
| Google | 全角110文字前後 |
| Yahoo | 全角110文字前後 |
| Googleモバイル | 全角55文字前後 |
| Yahooモバイル |全角30文字以内 |

```html
<meta name="description" content="サイトの説明文">
```

**検索エンジンクローラー除け**  
クローラーにURLのインデックスをさせない、文章内のリンクをたどらないよう知らせるための指定。  
完全に情報収集を遮断するものではないので、確実に行うならサーバー設定などが必要。  
ちょっとしたお札。  

```html
<meta name="robots" content="noindex,nofollow">
```

**ウェブアプリケーション名(HTML5で要素追加)**※ウェブアプリケーションのみ使用可  
[例]Gmail  
```html
<meta name="application-name" content="Gmail">
```

**文章作成に使用したツール・ソフトウェアの指定**  
通常使用しない。  
ページが自動生成された時にツール自身ページに出力するもの  
[例]Wordpress  
```html
<meta name="generator" content="WordPress 3.6.1" />
```

<a name="HTTP-EQUIV">http-equiv
---------------
**デフォルトCSSの指定**  
デフォルトで使用されるスタイルの指定。  
link要素で複数のCSSファイルを指定している場合、その中で優先利用するCSSファイルを指定する事ができる。  
```html
<meta http-equiv="default-style" content="default.css">
```

**リダイレクト・再読み込みの指定**  
[例]5分ごとに現在のページを読み込む  
```html
<meta http-equiv="Refresh" content="300">
```

[例]5秒後hoge.htmlにリダイレクト  
```html
<meta http-equiv="refresh" content="5; url=hoge.html">
```