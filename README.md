# rem.js

[![License MIT](https://img.shields.io/npm/l/rem.js.svg)](https://github.com/zhuweiyou/rem.js/blob/master/LICENSE)
[![NPM Version](https://img.shields.io/npm/v/rem.js.svg)](https://www.npmjs.com/package/rem.js)

移动端页面自动适配脚本 [在线演示](https://zhuweiyou.github.io/rem.js)，改造自 [amfe/lib-flexible](https://github.com/amfe/lib-flexible)

默认以设计稿宽 `750px` 为基础 `1rem = 100px`

比如设计稿中 `150px`，在 css 中就写 `1.5rem`

也可自定义 `data-psd` 为你的设计稿宽度

## 使用

**不建议使用 npm 安装**

- 建议直接把代码写在页面的 `<head>` 中，尽量让它早执行

```html
<script data-psd="750">!function(a){var b=window.document,c=b.documentElement,d=a?~~a.dataset.psd:750,e=1,f=1/e,g="orientationchange"in window?"orientationchange":"resize",h=b.createElement("meta");h.name="viewport",h.content="width=device-width, user-scalable=no, initial-scale="+f+", maximum-scale="+f+", minimum-scale="+f,c.firstElementChild.appendChild(h);var i=function(){var a=c.clientWidth;a/e>d&&(a=d*e),c.dataset.width=a,c.dataset.persent=100*(a/d),c.style.fontSize=100*(a/d)+"px"};i(),b.addEventListener&&window.addEventListener(g,i,!1)}(document.querySelector("script[data-psd]"));</script>
```

- 不太建议引用 URL

```html
<script src="//unpkg.com/rem.js" data-psd="640"></script>
```
