---
title: JS 學習筆記二 - Vue API
date: 2022-11-24 19:57:00
permalink: /pages/39c63e/
sidebar: auto
categories:
  - 教學
  - Vue.JS
tags:
  - Vue.JS
---

在對 Vue.JS 有了一點基本的載入後，就要來開始學習 Vue.JS 基本用法拉。

<!-- more -->

## 前言
在 Vue.JS 中，有兩架構寫法，第一種就是 [Composition API](#淺談-composition-api)，第二種就是 [Options API](#淺談-options-api)，接下來我們就要來去比較這兩種的差別。

## 淺談 Composition API
實務上我們比較少去使用 Composition API 去撰寫網頁，原因是不好看，也難以維護，大概看過去有個了解就好了。

```javascript
// 範例

// 先將 vue 這個套件的 ref 匯入進來
import { ref } from 'vue'

//使用 ref(0) 放入 counter
let counter = ref(0);

// 完成計數
const incrCounter = function() {
    counter.value += 1;
}
```

## 淺談 Options API
在實務上，我們很常利用 Options API的形式開發網頁，其中架構模式最好理解。直接看範例吧

```javascript
const app = {
  //  這是一個固定的方法，用於儲存變數。
  data (){
    return {
      // 在這個地方呢，會定義變數，會以 Object 的形式儲存。
      name: ''
    }
  },

  // 這是一個用於定義方法的 Object 
  methods: {
    sayHello(name) {
      return 'Hello, ' + name
    }
  },
  // 這是生命週期，我們在之後會提到
  created (){
    // 會在 Vue.JS 進入的時候，執行此方法，並在 Console中印出 "Hello, Andy"
    console.log(sayHello('Andy'))
  },
  // 這也是生命週期，我們之後會提到
  mounted (){
    // 會在 Vue.JS 掛載完元件時，執行此方法，並在 Console中印出 "Hello, Marry"
    console.log(sayHello('Marry'))
  }
}

// 將主程式掛載至選擇器 #app 上
Vue.createApp(app).mounted('#app');
```

## 兩個比較
由上面兩個例子可以比較出，Option API 會比較好懂，在未來我們也會以 Option API 開始介紹，只要再這有個概念就好。

## 相關文章

[《JS 學習筆記一》](/pages/1dea37/)

[《JS 學習筆記三 - 基本運算》](/pages/a3e20f/)
