<template{{#pug}} lang="pug"{{/pug}}>
  {{#pug}}
  .hello
    h1 \{{msg}}
    h2 这个是组件
  {{else}}
  <div class="hello">
    <h1>\{{ msg }}</h1>
    <h2>这个是组件</h2>
  </div>
  {{/pug}}
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
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
