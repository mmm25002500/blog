---
title: JS 學習筆記三 - 基本運算
date: 2022-11-24 20:15:57
permalink: /pages/a3e20f/
sidebar: auto
categories:
  - 教學
  - Vue.JS
tags:
  - Vue.JS
---

在上一章我們提到了 Composition API 和 Option API 的差別，其實兩個都可以寫出 Vue.JS 也各有優缺點，但在實務上大多都是以 Option API 作為首位開發選項，Option API更為好學，但如果想完整使用 Vue.JS 絕對不能少基本運算和變數定義。

<!-- more -->

## 定義變數
定義變數是在簡單不過的事情了，只要在 Vue.JS 的 data中定義就可以使用了。

### 了解定義和使用方式

首先我們先在 HTML 中給定 id 為 "app" 作為進入點，再來我們在裡面先顯示 number。
在兩個大括號中，我們必須輸入**表達式**，何謂表達式呢？變數、方法...都是表達式，但保留字並非表達式喔！
```html
<div id="app">
  <!-- 會顯示 1 -->
  {{ number }}
  <br />
  <!-- 會顯示 2 -->
  {{ number + 1 }}
  <!-- 會顯示 30 -->
  {{ number * 30 }}
  <!-- 會顯示 Hi -->
  {{ text }}
  <!-- 會顯示 true -->
  {{ isHappy }}
  <!-- 會顯示出 TershiXia -->
  {{ myParent.Father.name }}
  <!-- 會顯示出 392 -->
  {{ myParent.Mother.age - myParent.Mother.age }}
</div>
```

在 JS 的部份呢，我們需要在 data 內定義一個變數叫做 number，以呼應 html 要顯示的變數。
```javascript
data (){
  return {
    number: 1,
    text: 'Hi',
    isHappy: true,
    myParent: {
      Father: {
        name: 'TershiXia',
        age: 12
      },
      Mother: {
        name: 'ERROR404',
        age: 404
      }
    }
  }
}
```

### [實做] 寫出累加器
沒錯！在看完變數怎麼定義後，應該就有感覺了，原來只要在 data 裡面定義 number 就可以在畫面中出來值，我們就來實做個累加器吧。

```@click``` 是 Vue.JS 一個事件處理器，@click 就代表滑鼠點擊時要觸發的事件，我這邊沒有定義 Function，但也仍然可以使用表達式。
```html
<div id="app">
  {{ num }}
  <input type="button" text="點我+1(表達式)" @click="num += 1"/>
  <input type="button" text="點我+1(使用方法)" @click="addNum()"/>
</div>
```

可以看到我在 data底下新增了 methods，要記住 methods 是一個 Object，其中我定義了一個方法叫做 addNum，將原本的 data值加上1。
我這邊用了一個很怪的東西叫做 this，this這東西會指向我們的 vue，這裡準確來說是 data裡面的 num，用這方法幫我們把 num 加上1，在透過 Vue.JS 操作 DOM，幫我們在畫面中渲染出 num。
```javascript
data(){
  return {
    num: 0
  }
},
methods: {
  addNum () {
    this.num += 1
  }
}
```

## 定義方法
在前面的定義變數，我已經稍微介紹過了方法，在一般 JS 中，我們會用以下方式定義方法。

```javascript
// 一般方法
function func(){
  console.log('I Love TershiXia');
}

// 將變數作為方法用
const func2 = function {
  console.log('I want to kiss TershiXia');
}
```

而在 Vue 中我們可以這麼定義方法

```javascript
methods: {
  func3 (){
    console.log('TershiXia is cute');
  }
}
```

當然我們也可以使用 ES6 更新的箭頭函式(Arror Function)

```javascript
const func4 = () => {
  console.log('TershiXia is noob')
}
```

## 相關文章

[《JS 學習筆記二 - Vue API》](/pages/39c63e/)

[《JS 學習筆記三 - 基本運算》](/pages/a3e20f/)