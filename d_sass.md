## Sassをどう活かす？

----

## `@extend`

<div class="my-img"><img src="img/oocss-skin/2.png" alt=""></div>

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

#### OOCSSでは……

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

スキン → マルチクラスで実装してた

---

#### BEMでは……

```
<span class="button button_type_caution">Caution!!</span>
```

Modifier → マルチクラス

<div style="height:30px"></div>

#### SMACSSでは……

```
<span class="button button-caution">Caution!!</span>
```

サブクラス → マルチクラス

---

#### Sassなら……

```
<span class="button">Button!!</span>
<span class="button-caution">Caution!!</span>
```

```
.button {
  font-size:1.5em;
  padding:.5em 2em .4em;
  border:3px solid #000;
  border-radius:10px;
}

.button-caution {
  @extend .button;
  font-weight:bold;
  color:#fff;
  background:#FD3636;
  border-color:#BC2828;
}
```

---

### `@extend`のすごい点

* スキンのような概念を表現する方法が無かった
* マルチクラスを利用するしか無かった
* 見栄えの情報がHTMLに内包されていることに？
* プリプロセッサの過程を経ることでその問題を解決
