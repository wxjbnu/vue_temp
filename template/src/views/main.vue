<template{{#pug}} lang="pug"{{/pug}}>

  {{#pug}}
  .home
    h1 \{{msg}}
    input(type="text" v-model="commentContent")
    component(:is="'asyncCom'" v-if="showAsyncCom")
    button(@click="showAsyncCom = !showAsyncCom") 显示异步组件
    router-view
  {{else}}
  <div class="home">
    <h1>\{{ msg }}</h1>
    <input type="text" v-model="searchInputValue">
    <HelloWorld></HelloWorld>
    <component
      v-if="showAsyncCom"
      :is="'asyncCom'"></component>
    <button @click="showAsyncCom = !showAsyncCom">显示异步组件</button>  
    <router-view/>
  </div>
  {{/pug}}
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      msg: '首页',
      searchInputValue: '',
      showAsyncCom: false, // 异步组件
    }
  },
  components: {
    // asyncCom: resolve => {require(['./../components/asyncCom.vue'], resolve)}
    'asyncCom': () => import('./../components/asyncCom')
  },
  methods: {
    fetchPostList() {
      console.log(111)
    }
  },
  watch: {
    searchInputValue: {
      // 马上执行watch
      handler: 'fetchPostList',
      immediate: true
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped {{#less}}lang="less"{{/less}}>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
