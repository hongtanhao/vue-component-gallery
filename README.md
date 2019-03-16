# vue-component-gallery
vue component gallery sets born at superCounter in ksrcb(昆山农商银行项目)

## 在你的本地运行demo：
```bash
git clone https://github.com/hongtanhao/vue-component-gallery.git  # 获取源码
cd vue-component-gallery
npm/cnpm install
npm/cnpm run dev
path: '/table'  # demo 路由
```
## 定义组件
+ components目录下的 *WxfTable.vue*

## 使用组件
+ pages目录下的 *UseTable.vue*

路由`router/index.js`
```javascript
import Vue from 'vue'
import Router from 'vue-router'
import HelloWorld from '@/components/HelloWorld'
import UseTable from '@/pages/UseTable'

Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'HelloWorld',
      component: HelloWorld
    },
    {
      path: '/table',
      name: 'UseTable',
      component: UseTable
    }
  ]
})
```
项目入口 `main.js`
```javascript
// The Vue build version to load with the `import` command
// (runtime-only or standalone) has been set in webpack.base.conf with an alias.
import Vue from 'vue'
import App from './App'
import router from './router'

Vue.config.productionTip = false

/* eslint-disable no-new */
new Vue({
  el: '#app',
  router,
  components: { App },
  template: '<App/>'
})

```