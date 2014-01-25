# Compass CSS Sprite

[@Takazudo](https://twitter.com/Takazudo)

----

## super simple example

```
<span class="icon-face-cool"></span>
<span class="icon-face-sad"></span>
<span class="icon-face-wink"></span>
```

---

## SCSS

```
@import "icon/*.png";
@include all-icon-sprites;

.icon-face-cool { width:48px; height:48px; }
.icon-face-sad { width:48px; height:48px; }
.icon-face-wink { width:128px; height:128px; }

// デバッグ用

span {
  display:inline-block;
  border:3px solid #000;
}
```

```
$ compass compile
```

---

## Sprite!!!

![](demo/ex01-simple/images/icon-s51e5ca4f42.png)

---

## CSS!!!

```
.icon-sprite, .icon-face-cool, .icon-face-sad, .icon-face-wink {
  background: url('../images/icon-s51e5ca4f42.png') no-repeat;
}

.icon-face-cool {
  background-position: 0 -128px;
}

.icon-face-sad {
  background-position: 0 -176px;
}

.icon-face-wink {
  background-position: 0 0;
}

.icon-face-cool {
  width: 48px;
  height: 48px;
}

.icon-face-sad {
  width: 48px;
  height: 48px;
}

.icon-face-wink {
  width: 128px;
  height: 128px;
}

span {
  display: inline-block;
  border: 3px solid #000;
}
```

---

## Demo!!!

* [demo](demo/ex01-simple/html/1.html)

----

## 2 sprites example

```
<span class="face-cool"></span>
<span class="face-sad"></span>
<span class="face-wink"></span>
<span class="audio-headset"></span>
<span class="audio-keyboard"></span>
<span class="audio-speaker"></span>
```

---

## SCSS

```
@import "icon/audio/*.png";
@import "icon/face/*.png";
@include all-audio-sprites;
@include all-face-sprites;

.face-cool { width:48px; height:48px; }
.face-sad { width:48px; height:48px; }
.face-wink { width:128px; height:128px; }
.audio-headset { width:128px; height:128px; }
.audio-keyboard { width:128px; height:128px; }
.audio-speaker { width:32px; height:32px; }

// デバッグ用

span {
  display:inline-block;
  border:3px solid #000;
}
```

```
$ compass compile
```

---

## Sprites!!!

![](demo/ex02-2sprite-maps/images/icon/face-s820149b219.png) ![](demo/ex02-2sprite-maps/images/icon/audio-sf2be771957.png)

---

### CSS!!!

```
.audio-sprite, .audio-headset, .audio-keyboard, .audio-speaker {
  background: url('../images/icon/audio-sf2be771957.png') no-repeat;
}

.face-sprite, .face-cool, .face-sad, .face-wink {
  background: url('../images/icon/face-s820149b219.png') no-repeat;
}

.audio-headset {
  background-position: 0 0;
}

.audio-keyboard {
  background-position: 0 -128px;
}

.audio-speaker {
  background-position: 0 -256px;
}

.face-cool {
  background-position: 0 -128px;
}

.face-sad {
  background-position: 0 -176px;
}

.face-wink {
  background-position: 0 0;
}

.face-cool {
  width: 48px;
  height: 48px;
}

.face-sad {
  width: 48px;
  height: 48px;
}

.face-wink {
  width: 128px;
  height: 128px;
}

.audio-headset {
  width: 128px;
  height: 128px;
}

.audio-keyboard {
  width: 128px;
  height: 128px;
}

.audio-speaker {
  width: 32px;
  height: 32px;
}

span {
  display: inline-block;
  border: 3px solid #000;
}
```

---

## Demo

* [demo](demo/ex02-2sprite-maps/html/1.html)

----

## width, height example

```
$icon-sprite-dimensions: true;

@import "icon/*.png";
@include all-icon-sprites;
```

---

## Demo

* [demo](demo/ex04-width-height/html/1.html)

----

## Configurable variables example

Configure before `@import`.

```
// widthとheightも出力するか
$icon-sprite-dimensions: true;

// 画像間の隙間
$icon-spacing: 20px;

// X軸方向に繰り返すか
$icon-repeat: repeat-x;

// スプライトのベースクラス
$icon-sprite-base-class: '.myicon';

// 新しくスプライトが作られた時に古いものを削除するか
$icon-clean-up: true;

// スプライトの処理
@import "icon/*.png";
@include all-icon-sprites;
```

---

### Sprite!!!

![](demo/ex05-configuration/images/icon-s8f80a2636f.png)

----

## Layout example

```
$icon-layout: smart; // THIS!!!

@import "icon/*.png";
@include all-icon-sprites;
```

---

### vertical (default)

![](demo/ex06-layout/images/vertical.png)

---

### horizontal

![](demo/ex06-layout/images/horizontal.png)

---

### smart

![](demo/ex06-layout/images/smart.png)

---

### diagonal

![](demo/ex06-layout/images/diagonal.png)

----

## One by one example

```
<div class="faces">
  <span class="cool"></span>
  <span class="sad"></span>
  <span class="wink"></span>
</div>
```

---

### SCSS!!!

```
@import "icon/*.png";

.faces {
  .cool {
    @include icon-sprite(face-cool);
    width:48px;
    height:48px;
  }
  .sad {
    @include icon-sprite(face-sad);
    width:48px;
    height:48px;
  }
  .wink {
    @include icon-sprite(face-wink);
    width:128px;
    height:128px;
  }
}

// デバッグ用

span {
  display:inline-block;
  border:3px solid black;
}
```

---

### Demo!!!

* [demo](demo/ex03-custom-selector/html/1.html)

----

## Magic selectors example

```
<a href="#"></a>
```

---

### SCSS!

```
$button-sprite-dimensions: true;
@import "button/*.png";

a {
  display:block;
  border:3px solid #6EA56E;
  @include button-sprite(pushme);
}
```

---

### images I prepared

* `pushme.png`&nbsp;&nbsp;&nbsp;<img src="demo/ex07-magic-selectors/images/button/pushme.png" style="vertical-align:middle" alt="">
* `pushme_hover.png`&nbsp;&nbsp;&nbsp;<img src="demo/ex07-magic-selectors/images/button/pushme_hover.png" style="vertical-align:middle" alt="">
* `pusme_active.png`&nbsp;&nbsp;&nbsp;<img src="demo/ex07-magic-selectors/images/button/pushme_active.png" style="vertical-align:middle" alt="">
* `pushme_target.png`&nbsp;&nbsp;&nbsp;<img src="demo/ex07-magic-selectors/images/button/pushme_target.png" style="vertical-align:middle" alt="">

---

### CSS!!!

```
.button-sprite, a {
  background: url('../images/button-s42f973137b.png') no-repeat;
}

a {
  display: block;
  border: 3px solid #6EA56E;
  background-position: 0 -80px;
  height: 40px;
  width: 150px;
}
a:hover, a.pushme_hover, a.pushme-hover {
  background-position: 0 -160px;
}
a:target, a.pushme_target, a.pushme-target {
  background-position: 0 -40px;
}
a:active, a.pushme_active, a.pushme-active {
  background-position: 0 0;
}
```

---

### Demo!!!

* [demo](demo/ex07-magic-selectors/html/1.html)

----

## Helpers example

```
<span class="icon-face-cool"></span>
<span class="icon-face-wink"></span>
```

---

### SCSS

```
$icon: sprite-map("icon/*.png", $layout: smart);

.icon-face-cool {
  // spriteのURLを取得
  background-image: sprite-url($icon);
  // spriteの中から、face-coolのpositionを取得
  background-position: sprite-position($icon, face-cool);
  // face-coolのspriteの幅を取得
  width: image-width(sprite-file($icon, face-cool));
  // face-coolのspriteの高さを取得
  height: image-height(sprite-file($icon, face-cool));
}

.icon-face-wink {
  // face-winkの情報をまとめて取得
  background: sprite($icon, face-wink);
  // face-winkのspriteの幅を取得
  width: image-width(sprite-file($icon, face-wink));
  // face-winkのspriteの高さを取得
  height: image-height(sprite-file($icon, face-wink));
}

// デバッグ用
span {
  display:inline-block;
  border:3px solid black;
}
```

---

### Demo!!!

* [demo](demo/ex08-helpers/html/1.html)

----

続きは[CodeGrid](https://app.codegrid.net/)で
