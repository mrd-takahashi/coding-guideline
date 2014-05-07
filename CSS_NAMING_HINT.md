CSS 命名のヒント
===============

命名のヒント
----------------
『種類』と『役割』や『状態』などを組み合わせて考えます。  
[例] 大きさが同じでカラーが違うボタンの『送信』と『リセット』
```html
<form action="hoge.php" method="post">
  <dl>
    <dt>
      <label for="name">名前:</label>
    </dt>
    <dd>
      <input type="text" name="name" id="name">
    </dd>
    <dt>
      <label for="email">メールアドレス</label>
    </dt>
    <dd>
      <input type="text" name="email" id="email">
    </dd>
  </dl>
  <input type="submit" value="送信する" class="btn btn-send">
  <input type="reset" value="リセット" class="btn btn-reset">
</form>
```

```CSS
.btn {
  color: #000; /*黒*/
  background: #d5e1ee; /*薄いブルー*/
  text-align: center;
  width: 200px;
  height: 40px;
  margin-bottom: 20px;
  border-radius: 10px;
  }

.btn-send {
 color: #fff; /*白*/
 background: #f00; /*赤*/
}

.btn-reset {
 color: #999; /*明るいグレー*/
 background: #666; /*やや明るいグレー*/
}
```
[考え方]  
形状は幅200px高さ14pxの角Rボックスとする。要素の後は必ず20pxの空間を設けるので```.btn``` という共通クラスを用意します。  
『送信』と『リセット』には、それぞれの役割に応じた外観を与えるため、```.btn-send``` ```.btn-reset``` で外観を設定。  

```.btn``` だけを付与するaリンクやボタン要素がなければ、文字色や背景色の設定は不要ですが、、
```.btn-send``` ```.btn-reset```が一緒に記述されなかった場合、ブラウザのデフォルトスタイルなどが適用されて意図しない表示になる場合があります。  
それを避けたい場合はプロパティを設けます。  