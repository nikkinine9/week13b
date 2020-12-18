<template>
  <div id="app">
    <vue-tweets></vue-tweets>
    <vue-container></vue-container>
  </div>
</template>

<script>
import VueTweets from './components/Tweets.vue';
import VueContainer from './components/TweetContainer.vue'
export default {
  name: 'App',
  components: {
    VueTweets,
    VueContainer
  },
}
</script>

<style lang="scss">
body {
background-color: #2c3e50;
min-height: 100vh;
min-width: 100vw;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: 0px;
}
</style>
