<template>
  <nav-bar></nav-bar>
  <post-feed></post-feed>
  <add-post></add-post>
</template>


<script>
import NavBar from './components/NavBar.vue';
import PostFeed from './components/PostFeed.vue';
import AddPost from './components/AddPost.vue';
export default {
  name: 'App',
  components: {
    NavBar,
    PostFeed,
    AddPost
  }
}
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
  box-sizing: border-box;
}



#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
