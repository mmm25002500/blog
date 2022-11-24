---
title: JS 學習筆記一
date: 2022-10-02 19:14:30
permalink: /pages/1dea37/
sidebar: auto
categories:
  - 教學
  - Vue.JS
tags:
  - Vue.JS
---

在前端 javascript 框架中，有許多選擇，有 React.JS、Vue.js、Three.Js...等等，在這些框架中，每個框架都有各自獨特的功能，以便我們在網頁開發的時候更快速更順手。多虧了這些框架，在前端開發更為方便，有了框架，再也不是死板困難的Javascript。

<!-- more -->

## Vue.JS 介紹
Vue，是一款基於前端視圖開發的 javascript 漸進式框架。

Vue.js 提供 API，可以在資料和標籤進行綁定，也可以實作成一個又一個的元件(Componenets)。Vue.js 也提供了幾個生命週期讓使用者操作。同時 Vue.js 官方文件也寫得淺顯易懂，相比 JQuery 或其他官方文件，是難以理解的。

## Vue.js 的發展歷史
Vue.js 在 2013年 被 作者 [尤雨溪](https://zh.wikipedia.org/zh-tw/%E5%B0%A4%E9%9B%A8%E6%BA%AA) 開發而成。

[尤雨溪](https://zh.wikipedia.org/zh-tw/%E5%B0%A4%E9%9B%A8%E6%BA%AA) 本身在 Google 工作，先前開發 AngularJS，看到了許多AngularJS的缺點及優點，開發出了 Vue.JS，並在 2014年02月發布了 Vue.JS 版本0.8。

## 第一支程式 Hello World
首先先在 ```index.html``` 的 head 中匯入 vue.js的開發版本。
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/3.0.2/vue.global.js"></script>
```

然後在 ```body``` 中建立 app
```html
<div id="app">
    {{ msg }}
</div>
```
並在底下建立一個 javascript
```html
<script>
    var app = {
        data(){
            return {
                msg: 'Hello_World'
            }
        }
    }
    Vue.createApp(app).mount('#app');
</script>
```
此時已經可以執行，並在畫面中印出 "Hello_World" 字樣，那麼第一個網頁就算是成功拉。

Vue 會將資料連結至 DOM，這種資料連結是雙向，因此我們稱為雙向綁定。

## 結尾
看到這邊，相信聰明伶俐的你已經完成了第一個使用 Vue.JS 框架寫出的網頁，之後我們在這篇一起繼續學習吧！！！


## 相關文章

[《JS 學習筆記二 - Options API》](/pages/39c63e/)
