CSS
===============

+ [基本](#BASIC)
+ [命名規則](#NAMING)
+ [目次と見出し](#HEADING)
+ [インデントについて](#INDENT)
+ [共通・汎用スタイル](#COMMON)
  + 汎用クラスの使用について
+ [オプション](#OPTION)



<a name="BASIC">基本
----------------
+ セレクタのリセットは慎重に行う。アスタリスク(*)で全セレクタリセットはしない
+ インデント ⇒ 位置によって半角スペース1~2個。[インデントについて](#INDENT)
+ ID/CLASS名は小文字。単語をつなげる場合はハイフン(-)を用いる
+ タイプセレクタはなるべく付けない ⇒``` NG:ul.list```,```OK:.list```
+ セレクタを複数指定する場合は、カンマ(,)で区切り改行
+ プロパティはショートハンドを使用する
+ プロパティが1つまたは2つであれば1行で記述してもOK
+ 値が『0』の場合は単位を付けない
+ 透過指定をがある場合はrgba指定をする。その他は16進数で指定し、できる限り省略する
+ 要素同士の空間は極力margin-bottomで設定する ⇒ ページ毎の設定にズレを生じさせないため
+ 基本フォントサイズは16px〜14px(ブラウザの基本サイズが16px)
+ 最小フォントサイズは10px(Chromeの初期設定値は10px以下を全て10pxで描画する)
+ @importを使わずlinkを使用する
+ できる限り1ファイルに記述をまとめるようにする。ただし、リセット用のスタイルは別ファイルでもOK


<a name="NAMING">命名規則
----------------
+ 推測できる名称をつける
  + 短縮名を付ける場合は一般的に通じるかを考える(後日対応しても役割が推測できる名称にする) ⇒ [よく使われる短縮名](https://github.com/mrd-takahashi/coding-guideline/blob/master/SHORT_NAME.md)
  + サイズや色などを具体的に表す名称は避ける ⇒ Viewが変更された場合、名称と実際の表示の整合性がとれなくなるため
    + NG ⇒ ```.w960-box``` (w960pxのボックスの意) ボックスサイズが変更された場合、整合性がとれなくなる
    + NG ⇒ ```.red``` (文字色が赤いため) 色が変更になった場合、整合性がとれなくなる
    + OK ⇒ ```.profile-box``` (プロフィールに使用するボックスの意) ボックスサイズが変更されても、プロフィールに関わる要素である事は変わらない
    + OK ⇒ ```.txt-error```  (エラー用の文字色）文字色が変更されても、エラー文字の色設定である事は変わらない
    + OK ⇒ ```.mab10```  (margin-bottom: 10px) 場合によって使用可。 ただし、規則性がなければならない。[『共通・汎用スタイル』参照](#COMMON)
+ jQueryなどjs用のidまたはclassにはプレフィックス（接頭辞）```js-``` を付与する
  + ```js-```  を持つidまたはclassには構造やスキン（見た目）の設定をしない
  + ```js-```  とは別のidやclassを付与する事で構造やスキン（見た目）の設定をする


⇒ [命名のヒント](https://github.com/mrd-takahashi/coding-guideline/blob/master/CSS_NAMING_HINT.md)  
⇒ [よく使われる短縮名](https://github.com/mrd-takahashi/coding-guideline/blob/master/CSS_NAMING_HINT.md)


参考:<a href="http://www.slideshare.net/MayuKimura/css-25547100" target="_blank">今必要なCSSアーキテクチャ</a>  
参考:<a href="http://d.hatena.ne.jp/in0in0/20100208/1265657205">OOCSS(Object-Oriented CSS)の考え方</a>


<a name="HEADING">目次と見出し
----------------
###目次
ファイル上部に番号付き・大文字で記載。役割やディレクトリ名を付与する（第三者が見て分かりやすい名称）。 
```css  
/*********************************  
0.BASE  
1.HEAD  
2.LAYOUT
  2-1.LAYOUT-INDEX
  2-2.LAYOUT-PAGE 
3.SIDE  
4.FOOT  
*********************************/
```

###見出し  
大見出しと小見出しの2つを使い、記述を整理します。  
```css  
/*********************************

2.LAYOUT

*********************************/

/*2-1.LAYOUT-INDEX*/
#index img {
  border: 0;
  vertical-align: top;
  }
  
#index a img {border: 0;}
#index a,
#index a:link,
#index a:visited {color: #fff;}
```


<a name="INDENT">インデントについて
----------------
インデントは半角スペースを使用します。  
プロパティが1つまたは2つの場合は1行で記述してもOKです。  
下記□は半角スペースを表します。
```css  
.alignleft□{
□□margin:□0 4px 4px;
□□float:□left;
□□}

img□{border:□0;□vertical-align:□top;}
```

*キーボードの[tab]を使い、効率よくインデントする方法*  
> DWの場合は設定を下記に変更する  
> [環境設定] ⇒ [コードフォーマット]  
> ⇒ 『インデント』チェック  
> ⇒  使用:2スペース  
> ⇒  タブサイズ2,『スペースとして挿入』チェック  


<a name="COMMON">共通・汎用スタイル
----------------
以下は必ず記述しなければならない共通スタイルです。プロパティは変更の必要があれば各案件用に記述する事。

+ ```body``` コンテンツ全体の基本設定。テキストサイズは16~14pxくらい。行間は単位なしで1.4~
+ ```.clearfix``` float解除用のクラス。汎用スタイル
+ ```img``` 画像が描画された時にborderを無効にし、縦方向配置位置を上部に設定する
+ ```a img``` リンクがある画像からborderを無効にする
+ ```a``` ```a:link``` ```a:hover``` ```a:visited``` リンク・マウスオーバー・訪問済みの基本設定
+ ```.alignleft``` 要素を左にfloatする。汎用スタイル
+ ```.alignright``` 要素を右にfloatする。汎用スタイル
+ ```p``` パラグラフ（段落）の基本設定
+ ```.note``` 注釈テキストなどに使うクラス。汎用スタイル

位置はbodyの直下とします。
```css 
body {
  font: 16px "ヒラギノ角ゴ Pro W3", "Hiragino Kaku Gothic Pro", "メイリオ", Meiryo, Osaka, "ＭＳ Ｐゴシック", "MS PGothic", sans-serif;
  line-height: 1.4;
  background: #000;
  color: #fff;
  text-align: center;
  margin: 0 auto;
  padding: 0;
  -webkit-text-size-adjust: none; ⇒スマホ用設定。iPhoneやiPadで傾けた時のフォント拡大を防ぐ。PCのみは不要
  }

/*COMMON STYLE*/  
.clearfix:after {
  content: ""; 
  display: block; 
  clear: both;
  }
  
img {border: 0; vertical-align: top;}

a img {border: 0;}

a,
a:link,
a:visited {color: #ee1a02; text-decoration: underline;}
a:hover {text-decoration: none;}

.alignleft {margin:0 4px 4px; float: left;}
.alignright {margin:0 4px 4px; float: right;}

.alignleft:after,
.alignright:after {
  content: ""; 
  display: block; 
  clear: both;
  }
  
p {margin-bottom: 20px;}

.note {font-size: 12px; margin-bottom: 20px;}

```


※```.alignleft``` ```.alignright``` はWordpressの『投稿』で『メディア』を呼び出して画像を配置する際に使用されるclass名と同名です。  
この他に```.aligncenter``` も存在します。  
オリジナルテーマを作った時はこの設定も入れた方が良いため、共通スタイルに組み込まれています。


###汎用クラス(marginやpaddingなどのモジュール)の使用について  
```CSS
.ma10 {margin: 10px;}
.mt10 {margin-top: 10px;}
.mr10 {margin-left: 10px;}
.mb10 {margin-bottom: 10px;}
.ml10 {margin-left: 10px;}

.pa20 {padding: 20px;}
.pt20 {padding-top: 20px;}
.pr20 {padding-left: 20px;}
.pb20 {padding-bottom: 20px;}
.pl20 {padding-left: 20px;}

-以下略-
```  

OOCSSなどのオブジェクト指向のCSS設計では構造とスキン（見た目）を分離して考えるため、marginやpadding、floatだけの汎用クラスが存在します。
これらはどの要素に対しても使用できますが、

1. 汎用クラスが膨大になった場合、すべてを把握する事が難しい  
1. コーディングの習熟度によって適切に使われない場合がある    
1. CSSの肥大化  

という問題が生じます。  
サービスイン後の機能拡張等でCSSの肥大化は避けられないため、サービスイン直後の状況としては極力肥大化をさけるべきです。  
そのため、margin・paddingの汎用クラスを設ける場合は最低限のものとします（非推奨クラスです）。

+ 設定を設けるかは開発側と協議（デザイン側では非推奨です）
+ 値は規則性を持つ（倍数）
+ 1カ所以上、永続的に使用する可能性がある ⇒ 1カ所だけであれば、付与されている既存クラスにプロパティとして追加する、インラインで書くなどで対応する
+ 新規追加したセレクタは、margin/paddingのみの汎用クラスと組み合わせず、追加したセレクタにプロパティとして設定する
  
  
####汎用クラス命名規則  
最小の値が『5』であれば、5,10,15,20…と倍数にします。　　
> OK：5,10,15,20,25,30,35…  
> NG：2,5,10,15,20,25,30,35…

| class name |  |
|:-----|:-----|
| .ma10 | margin: 10px; |
| .mt10 | margin-top: 10px; |
| .mr10 | margin-right: 10px; |
| .mb10 | margin-bottom: 15px; |
| .ml10 | margin-left: 10px; |
| .pa10 | padding: 10px; |
| .pt10 | padding-top: 10px; |
| .pr10 | padding-right: 10px; |
| .pb10 | padding-bottom 10px; |
| .pl10 | padding-left: 10px; |


マイナス値を設定する場合は冒頭に『n』を付けます（n = negative）  
[例].nmt10 ⇒ margin-top:-10px;


<a name="OPTION">オプション
----------------
必要があれば使用します（任意）  

**z-indexを多用した時**  
以下のようなメモがあると後日追加する時にわかりやすい  
```css  

/*
Z-INDEX
********************************  
header = 10
article header h1=15
article header nav=20
.topic-path = 30

article header.top=15 -index only
.top-main-image = 20 -index only
.news.top = 30 -index only
.game-info = 30 -index only

SP ONLY
.top-main-sp = 20 -index SP only
article header.top-sp h1 = 30 -index SP only
.menu-tab = 40 -index SP only
.menu-sp =  40 -index SP only
*********************************/
```
