# vuex

> 专门为vue.js 应用程序开发的状态管理模式……

## vuex 是什么

el:

```vue
new vue({
  
})
```

这个状态字管理应用包含一下几个部分

- state 
- view
- actions

当我们的应用遇到多个组件共享状态时，单向数据流的简洁性就很容易被破坏

- 多个视图依赖同一状态
- 来自不同视图的行为需要变更同一状态

### 创建一个数据仓库

```javascript

Vue.use('vuex');
const store1 = new Vuex.Store({
  // state: 状态，用来保存状态
});
new Vue({
  el: '#app',
  router,
  store: store1		//在vue实例中就会多一个属性 $store
});
export default store1

// 在别的文件引入时 如果该文件名的 index.js 则可以省略 ，webpack 默认查找 index

```

- state

  状态，用来保存状态（数据）的属性，保存原始数据的属性

  > 是一个对象

​	

- getters

  如果我们在应用中需要根据某个条件的源数据中动态获取，那么就需要使用 getters

  接受4个参数

  ```vue
  getters:{
    goodsInfo(state) {
      return state.goods.filter(item => {
        return 
      })
    }
  }
  ```

  ​

  > 类似计算属性

- mutations

  如果需要修改 state ，必须通过mutations 来处理

  ```vue
  mutations: {
      setDetailId(state,id){
          console.log(arguments);
  		console.log()
      }
  }
  ```

- commit

  通过commit 提交一个事物，这个事物必须和mutations 对应

