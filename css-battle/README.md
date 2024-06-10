# CSS Battle

We're doing a battle together at https://cssbattle.dev/

## Daily Target

We did this target: https://cssbattle.dev/play/WkQVfaBd5YZAxAAgmtWt

<details>
<summary>Solution</summary>

```html
<style>
  * {
    background: radial-gradient(circle, #085328 55px, #1F7D3B 0 85px, #2F9947 0 115px, #49C85B 0);
  }
</style>
```
</details>

## Target 153

https://cssbattle.dev/play/153

<details>
<summary>Checkerboard</summary>

```html
<div></div>
<style>
  body {
    display: grid;
    place-items: center;
    background: #E3516E;
  }
  div {
    width: 200px;
    height: 200px;
    background:
      radial-gradient(circle at 60px 100px, #E3516E 10px, #0000 0) 0 0 / 80px 200px,
      radial-gradient(circle at 20px 60px, #FADE8B 10px, #0000 0) 0 0 / 80px 80px,
      radial-gradient(circle at 60px 20px, #FADE8B 10px, #0000 0) 0 0 / 80px 80px,
      conic-gradient(#E3516E 25%, #FADE8B 0 50%, #E3516E 0 75%, #FADE8B 0) 0 0 / 80px 80px;
  }
</style>
```
</details>

## Target 180

This was part of the second round of CSS Battles! https://cssbattle.dev/play/180
Looked into units like `q`.

<details>
 <summary>Kuwait - code golfed</summary>

```html
<style>*>*{margin:0;border-top:100px solid#13AA4B;border-bottom:100px solid#EC1E25;border-left:127q solid#000
```
</details>

## Target 157

This was part of the second round of CSS Battles! https://cssbattle.dev/play/157
The `-webkit-box-reflect` was new to some of us 🙂

<details>
 <summary>Monopoly</summary>

```html
<div class="head">
  <div class="hat"></div>
  <div class="eyes"></div>
  <div class="mustache"><div></div></div>
</div>
<style>
  body {
    background: #E38F66;
    display: grid;
    place-items: center;
  }
  .head {
    width: 180px;
    height: 220px;
  }
  .hat {
    height:50%;
    background:#FFFBDA;
    margin:0 30;
    border-radius: 50% 50% 0 0;
    position: relative;
  }
  .hat::after {
    content: '';
    width:45vw;
    height:20px;
    background:#FFFBDA;
    border-radius:10px;
    position:absolute;
    left:-30;
    bottom:0;
  }
  .eyes {
    background: radial-gradient(circle at 120px 32px, #0000 10px, #FFFBDA 0 20px, #0000 0),radial-gradient(circle at 60px 32px, #FFFBDA 10px, #0000 0);
    height: 70
  }

  .mustache {
    margin-left: 45;
    width: 40px;
    height: 40px;
    -webkit-box-reflect: right 10px;
  }
  .mustache>*{
    background: #FFFBDA;
    width: 100%;
    height: 100%;
    border-radius: 50% 50% 50% 0;
    transform: rotate(45deg)
```
</details>
