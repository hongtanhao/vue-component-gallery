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
## 定义table组件
+ components目录下的 `WxfTable.vue`

## 使用table组件
+ pages目录下的 `UseTable.vue`

其中：`UseTable.vue` 代码片段说明
表格数据结构必须这样：
```javascript
export default {
  name: 'UseTable',
  data() {
    return {
      dataTable: {
        display: {
            textAlign: 'center', // 表头文本排列样式
            rowHeight: '40', // 行高
            style: 'normal', // 表格风格
            thHeight: '40'
        },
        tcols: [// 数组长度代表了列数
            {
              name: 'order',
              label: '序号' // 表头显示的文本值
            },
            {
              name: 'name',
              label: '姓名' // 表头显示的文本值
            }
        ],
        trows: [// 数组长度代表了行数
            {
              order: '1', // 必须取tcols每一项中 `value`
              name: '王小虎'
            }
        ]
      }
    };
  }, 
```

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
## 表格分页器
+ components目录下的 `WxfSorter.vue`