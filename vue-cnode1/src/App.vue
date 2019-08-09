<template>
  <div id="app">
    <Header></Header>
    <div>
      <router-view name='main'></router-view>
    </div>
  </div>
</template>

<script>
import Header from './components/Header'
import PostList from './components/PostList'
export default {
  name: 'App',
  components: {
    Header,
    PostList
  }
}
</script>

<style>
  *{margin:0;padding:0;}
  body{
    background: #e1e1e1;
  }
  main{
    width: 88%;
    margin: 0 auto;
  }
</style>
