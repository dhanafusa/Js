# 初めに

この授業では、JavascriptというHTMLとCSSと組み合わせて使う言語を学んでいきます。  
VSCODEを使用して授業を行っていきますが、設定してほしい拡張機能があります。それ以外は各自自由に設定してください。  
  

## １.拡張機能

  

- LiveServer

  

![](https://github.com/dhanafusa/Js/blob/main/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202024-09-24%20131424.png)  

  

- IntelliCode  
  

![](https://github.com/dhanafusa/Js/blob/main/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202024-09-24%20131544.png)  

  

- Prettier

  

![](https://github.com/dhanafusa/Js/blob/main/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202024-09-24%20131642.png)  

Prettierは拡張機能の導入だけでは動作しませんので下記URLを参考に設定してください。  
[https://ralacode.com/blog/post/vscode-prettier/](https://ralacode.com/blog/post/vscode-prettier/ "https://ralacode.com/blog/post/vscode-prettier/")  

  

エディタの設定は以上になります。  
JavascriptはCSSと組み合わせて動きのあるページを作成することができます。

それで、今後必要なCSSアニメーションの基礎について簡単に学んでいきます。

  

## ２．CSSトランジション(transition)

CSSトランジションは、要素のスタイルが変化する際に、その変化を滑らかに行う機能です。これにより、ウェブページの視覚的な変化をより自然で魅力的なものにできます。

  

### 基本的な使い方

CSSトランジションは、`transition`プロパティを使用して定義します。

  

HTMLファイルは、以下のようにbodyタグの中に記述します。

``` html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body> 
   <div class="element"></div>
  </body>
</html>
```

  

CSSファイルは、`style.css`として以下のように記述します。

``` css
.element {
  width: 100px;
  height: 100px;
  background-color: blue;
  transition: all 0.3s ease;
}

.element:hover {
  width: 200px;
  background-color: red;
}
```

この例では、要素にマウスを乗せると、幅と背景色が0.3秒かけて滑らかに変化します。

  

### トランジションのプロパティ

トランジションには以下の主要なプロパティがあります：

1. `transition-property`: 変化させるプロパティを指定(すべてであればall、幅だけ変化させたい場合はwidth)
2. `transition-duration`: トランジションの継続時間を設定
3. `transition-timing-function`: トランジションの進行度合いを制御
4. `transition-delay`: トランジション開始までの遅延時間を設定

これらは短縮形で記述することもできます：

  

``` css
.element {
  transition: [property] [duration] [timing-function] [delay];
}
```

  

### タイミング関数

タイミング関数は、トランジションの進行度合いを制御します。主な値には以下があります：

- `ease`: デフォルト。ゆっくり始まり、速くなり、そしてゆっくり終わる
- `linear`: 一定の速度で変化
- `ease-in`: ゆっくり始まり、徐々に加速
- `ease-out`: 速く始まり、徐々に減速
- `ease-in-out`: ゆっくり始まり、加速し、そしてゆっくり終わる

カスタムのタイミング関数も`cubic-bezier()`関数を使って定義できます。

  

### 複数のプロパティに対するトランジション

複数のプロパティに対して異なるトランジションを適用することも可能です。

  

``` css
.element {
  transition: width 0.3s ease, background-color 0.5s linear;
}
```

  

  

## ３．CSSトランスフォーム (Transform)

トランスフォームは、要素の形状や位置を変更するためのCSSプロパティです。要素を回転させたり、拡大縮小したり、移動したりすることができます。主なトランスフォーム関数:

1. `translate(x, y)`: 要素を水平(x)と垂直(y)に移動
2. `scale(x, y)`: 要素を水平(x)と垂直(y)に拡大縮小
3. `rotate(angle)`: 要素を指定した角度だけ回転
4. `skew(x-angle, y-angle)`: 要素を水平と垂直に傾ける

  

HTMLファイルは、以下のようにbodyタグの中に記述します。

``` html
<div class="box"></div>
```

  

CSSファイルは、以下のように記述します。

``` css
.box {
  width: 100px;
  height: 100px;
  background-color: gold;
}
.box:hover {
  transform: translate(50px, 20px) rotate(45deg) scale(1.5);
}
```

この例では、要素を右に50px、下に20px移動し、45度回転させ、1.5倍に拡大しています。  
  
また、トランスフォームとトランジションを組み合わせることもできます。

CSSファイルを以下のように追記変更します。

  

``` css
.box {
  width: 100px;
  height: 100px;
  background-color: gold;
  transition: transform 0.3s linear; /* 追記 */
}
.box:hover {
  transform: translate(50px, 20px) rotate(45deg) scale(1.5);
}
```

  

  

## ４．練習問題

  

以下のように、ハンバーガーアイコンをホバーするアニメーションを作成して提出してください。以下のHTMLとCSSを使用し作成すること。

  

![](https://github.com/dhanafusa/Js/blob/main/chrome-capture-2024-9-24.gif)  

  

``` html
<button class="hamburger">
   <span class="line"></span>
   <span class="line"></span>
   <span class="line"></span>
</button>
```

  

``` css
.hamburger {
  width: 40px;
  height: 40px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.line {
  width: 100%;
  height: 3px;
  background: #333;
  transition: all 0.3s ease;
}
```
