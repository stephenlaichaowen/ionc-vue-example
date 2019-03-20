---
prev: false
next: false
---

# 🔨 使用 Ionic 4 + Vue 建立一個簡單的行動裝置應用

![](https://www.javascripttuts.com/images/thumbnails/ionic-vue-course-debut.png)


## 前言


Ionic 是一個專為行動裝置設計的一款受歡迎的 UI 框架. 在版本 4.0 之前 ionic 和 angular 和 typescript 綁在一起, 也就是說想要使用 ionic UI 組件必須學習 angular 和 typescript. 而 angular 和 typescript 的學習門檻對初學者來說挺高的. 4.0 版本後 ionic 團隊鬆開了對 angular / typescript 的綁定, 也就是說我們可以使用任何的 javascript 框架 (angular, vue, react, jquery) 或 vanilla javascript 搭配 ionic 開發行動裝置 app. 對於開發者來說是一大福音, 因為又多了另一種使用者介面可以選擇及使用.

> Ionic is an open source UI tool kit using web technologies, traditionally ionic relies heavily on angular, in version 4, ionic team let us build ionic based project with any javascript framework

<br><br>

## 使用 vue-cli 建立專案 

+ 安裝 vue-cli
```
npm install -g @vue/cli-service-global
```
+ 建立專案
```
vue create ionic-vue-example
```
+ 安裝 ionic/vue 和 ionic/core
```
npm i @ionic/vue @ionic/core
```

產生出來的專案長這樣

<img style="box-shadow: 0 0 20px rgba(72,98,85, 0.6)" src="https://cdn.glitch.com/e2d0de36-c372-4b42-8f8f-5dea2faa4285%2Fvue-cli.jpg?1553063649643">

<br><br>

## 測試 Ionic 組件

+ 在 main.js 加入以下代碼
```
import Ionic from '@ionic/vue'

Vue.use(Ionic)
```
+ 在 components/HelloWorld.vue 刪除 template 和 style 的內容. 
+ 在 views/Home.vue 刪除 img 及 HelloWorld 組件的屬性, 在 template 內加入 
```
<ion-label>Label</ion-label>
<ion-button @click="handleClick">Default</ion-button>
<ion-item>
  <ion-label position="floating">您的姓名</ion-label>
  <ion-input :value="myInput" @input="myInput = $event.target.value"></ion-input>
</ion-item>
```
注意 : 雙向綁定 v-model 不能正常動作, 所以改用 :value 及 @input

<br>

#### Demo
---
<img style="box-shadow: 0 0 20px rgba(72,98,85, 0.6)" src="https://cdn.glitch.com/e2d0de36-c372-4b42-8f8f-5dea2faa4285%2F20190320_153527.gif?1553067408050">

<br><br>

## 建立 Reddit clone /r/aww 行動裝置 APP

+ 使用 axios 遠端讀取 reddit API
+ 在 HelloWorld.vue 加入 ion-header, ion-list
+ Demo
  
<img style="box-shadow: 4px 4px 20px rgba(0, 0, 0, .3)" src="https://cdn.glitch.com/e2d0de36-c372-4b42-8f8f-5dea2faa4285%2F20190320_172914.gif?1553074219161">

<br><br>



### 心得與感想

我深深的感受到現代前端框架技術的進步及強大, 透過 nodejs 管理專案結構, webpack 整合不同的框架並打包, 讓產生應用程序變得簡單容易許多. 這個案例結合 ionic + vue 是個有趣的例子, 因為 vue 好用而且受歡迎度越來越廣, 所以連許多原本封閉的技術如 ionic 現在都支援 vue 了. 

### Q & A

+ vue-cli build 出來的專案資料夾檔案太多, 容量太大, 沒辦法部署到雲端服務如 Github, 該怎麼解決呢?
  - 目前還沒有 solutions...

### 程式碼
+ [Github](https://github.com/stephenlaichaowen/ionc-vue-example)

### 參考資料 :
+ [Ionic 4 + Vue Basics - Reddit Clone](https://www.youtube.com/watch?v=o7rb1S2Txfw&t=130s)
+ [Ionic Framework Docs](https://ionicframework.com/docs)

