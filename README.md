# Stylus mixins

## Install
```sh
npm i stylmixs -D
```
```styl
@import 'stylmixs'
```

## fface()
```styl
// stylus
fface('Inter', 'fonts/inter-300-light', 300, normal)
```
```css
/* css */
@font-face {
  font-family: 'Inter';
  src: url("fonts/inter-300-light.woff2") format('woff2'), url("fonts/inter-300-light.woff") format('woff'), url("fonts/inter-300-light.ttf") format('truetype');
  font-weight: 300;
  font-style: normal;
  font-display: swap;
}
```

## column()
integer values from 1 to 12
```styl
// stylus
.element
  column(2)
```
```css
/* css */
.element {
  width: 16.66%;
}
```

## placeholder()
```styl
// stylus
.input
  +placeholder()
    font-weight 300
```
```css
/* css */
.input::-webkit-input-placeholder {
  font-weight: 300;
}
.input:-moz-placeholder {
  font-weight: 300;
}
.input::-moz-placeholder {
  font-weight: 300;
}
.input:-ms-input-placeholder {
  font-weight: 300;
}
```

## gap()
```styl
// stylus
.box
  gap(30px)
```
```css
/* css */
.box {
  padding-left: 30px;
  padding-right: 30px;
}
```

## pad()
```styl
// stylus
.box
  pad(30px)
```
```css
/* css */
.box {
  padding-top: 30px;
  padding-bottom: 30px;
}
```

## fs()
integer values from 1 to 12
```styl
// stylus
.message
  fs(20, 28)
```
```css
/* css */
.message {
  font-size: 1.25em;
  line-height: 1.4em;
}
```

## overlay()
```styl
// stylus
.overlay
  position relative
  &:after
    +overlay()
      background-color rgba(#000, .5)
```
```css
/* css */
.overlay {
  position: relative;
}
.overlay:after {
  content: '';
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0,0,0,0.5);
}
```

## hidebox()
```styl
// stylus
.file
  &__input
    hidebox()
```
```css
/* css */
.file__input {
  position: absolute;
  z-index: -1000;
  overflow: hidden;
  clip: rect(0 0 0 0);
  height: 1px;
  width: 1px;
  margin: -1px;
  padding: 0;
  border: 0;
}
```

## mq()
```styl
// stylus
+mq(960px)
  .query
    display none
```
```css
/* css */
@media screen and (max-width: 960px) {
  .query {
    display: none;
  }
}
```

## ts()
```styl
// stylus
.button
  ts(color, background-color)
```
```css
/* css */
.button {
  transition: color .25s ease-in-out, background-color .25s ease-in-out;
}
```

## ratio()
```styl
// stylus
.aspect-ratio
  ratio(16, 9)
```
```css
/* css */
.aspect-ratio {
  padding-bottom: 56.25%;
  height: 0;
}
```
