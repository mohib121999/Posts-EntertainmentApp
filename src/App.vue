<template>
  <div id="app">
    <header>
      <h3>Entertainment App</h3>
      
    </header>
    <subreddits category="food"> </subreddits>
    <subreddits category="sports"> </subreddits>
    <subreddits category="space"> </subreddits>
    <subreddits category="art"> </subreddits>
    <subreddits category="movies"> </subreddits>
    <subreddits category="funny"> </subreddits>

  </div>
</template>

<script>
import subreddits from './components/subreddits'

export default {
  name: 'app',
  components: {
    subreddits

  }
}
</script>

<style>
  body{
    font-family: arial;
    color: #666666;
    background: #f4f4f4;
    margin:0;
    padding:0;
  }

  a{
    text-decoration: none;
  }
  header{
    background: coral;
    color:#ffffff;
    padding:10px;
    text-align: center;
  }
</style>
