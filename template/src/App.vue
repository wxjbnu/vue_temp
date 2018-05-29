<template{{#pug}} lang="pug"{{/pug}}>
  {{#pug}}
  #app
    router-view
  {{else}}
  <div id="app">
    <router-view/>
  </div>
  {{/pug}}
</template>

<script>
export default {
  name: 'App'
}
</script>

<style {{#less}}lang="less"{{/less}}>
html, body{
  height: 100%;
  margin: 0;
  padding: 0;
  font-size: 16px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
@media screen and (min-width: 769px) {
  html, body{
    /* font-size: 60px; */
  }
}
@media screen and (max-width: 768px) {
  html, body{
    /*font-size: 60px;*/
  }
  
}
</style>
