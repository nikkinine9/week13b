<template>
<div class="wrapper">
<button class="button is-success" @click="toggleView">Toggle View</button>
  <div id="tweets" :class="{'list-view': listView}">
    <article class="tweets" v-for="(tweet, index) in tweets" :key="index">
      <div class="tweet">
      <h4>{{ tweet.author }}</h4>
      <h6>{{ tweet.date }}</h6>
      <p>{{ tweet.text }}</p>
      </div>
    </article>
  </div>
</div>
</template>

<script>

export default {
  name: 'vue-tweets',
  data() {
    return {
      listView: false, 
      tweets: [
        {
        author: 'James',
        date: 'December 12, 2020',
        text: 'Hello world I am a tweet!'
       },
       {
        author: 'Karen',
        date: 'December 11, 2020',
        text: 'It works!!!'
       },
       {
        author: 'Dhwani',
        date: 'December 10, 2020',
        text: 'You are muted!!'
       },
      ]
    }
  },
  methods: {
    toggleView(){
      this.listView = !this.listView;
     }
  }
}
</script>

<style scoped>
#tweets {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
  padding: 1rem;
  color: ivory;
}

#tweets.list-view {
  grid-template-columns: 1fr;
}

article {
  padding: 1rem;
  margin: 1rem;
  background-color: #2c5035;
}

.tweets {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  margin: 5px 0;
}

.tweet {
  flex: 1;
  border: 1px solid black;
  margin: 2px;
  padding: 10px;
}

@media screen and (max-width: 991px) {
  .tweets .tweet {
    margin-bottom: 5px;
    flex-basis: 40%;
  }
  .tweets .tweet:last-child {
    margin-bottom: 5px;
    flex-basis: 100%;
    margin: 0;
  }
 }
</style>