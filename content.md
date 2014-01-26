# Compass CSS Sprite

[@Takazudo](https://twitter.com/Takazudo)

----

# OOCSS

----

## OOCSSとは

* Object Oriented CSS
* Nicole Sullivan (YAHOO!)
* オブジェクト指向っぽく考えて整理しよう
* レゴみたいに組み合わせてページをつくろう

----

## こういうのがダメ

図

---

```
#main h2 {
  ...
}
#main .contact .header h2 {
  ...
}
#sidebar h2 {
  ...
}
```

----

## なぜダメか

* 上書き合戦になってしまう
* 同じ部品を使いまわせない
* 詳細度を気にしないといけなくなる
* `!important`だらけになる
* 結果的にパフォーマンス落ちる

---

```
#main h2 { ...  }
#main .contact .header h2 { ...  }
#sidebar h2 { ...  }
#sidebar .nav2 h2 { ...  }
#sidebar .related .header h2 { ...  }
#main .related h2 { ...  }
#main .anotherTitle h2 { ...  }
#main .anotherHeadingWrap h2 { ...  }
```

----

## レゴみたいに考える

図

---

## 一つ一つがレゴのパーツ

```
.heading {
  ...
}
.heading2 {
  ...
}
.heading3 {
  ...
}
.heading4 {
  ...
}
```

レゴの部品: CSS Object

---

図

----

## スキン

* プログラムでいう「継承」と近い概念
* 共通項目を一つのモジュールに定義
* バリエーションをスキンとして定義
* マルチクラスで実装

---

図

---

図

---

<div class="my-img"><img src="img/button_base.png" alt=""></div>

```
<span class="button">Button!!</span>
```

```
.button {
  font-size:1.5em;
  padding:.5em 2em .4em;
  border:3px solid #000;
  border-radius:10px;
}
```

---

<div class="my-img"><img src="img/button_caution.png" alt=""></div>

```
<span class="button caution">Caution!!</span>
```

```
.caution {
  font-weight:bold;
  color:#fff;
  background:#FD3636;
  border-color:#BC2828;
}
```

---

<div class="my-img"><img src="img/button_pdf.png" alt=""></div>

```
<span class="button pdf">Download PDF!!</span>
```

```
.pdf {
  background:#ECE4AB;
  border-color:#D9D29E;
  padding-left:1.5em;
}
.pdf:before {
  content: '';
  display:inline-block;
  width:22px;
  height:22px;
  background:url(imgs/acrobat.png);
  vertical-align:-2px;
  margin:0 6px 0 0;
}
```

---

<div class="my-img"><img src="img/button_play.png" alt=""></div>

```
<span class="button play">Play sound!!</span>
```

```
.play {
  background:#C3E6EA;
  border-color:#AECDD0;
  padding-left:1.5em;
}
.play:before {
  content: '';
  display:inline-block;
  width:22px;
  height:22px;
  background:url(imgs/play.png);
  vertical-align:-2px;
  margin:0 6px 0 0;
}
```

----

# BEM

----

# SMACSS

----

続きは[CodeGrid](https://app.codegrid.net/)で
