<template>
<div class="tweet">
  <br>
<button class="button is-success" @click="toggleView">Toggle View</button>
  <div id="tweets" :class="{'list-view': listView}">
    <article class="tweet" v-for="(tweet, index) in tweets" :key="index">
      <h4>{{ tweet.author }}</h4>
      <h6>{{ tweet.date }}</h6>
      <p>{{ tweet.text }}</p>
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
      if(this.listView == true){
        document.querySelector('button').innerText = "List View";
      }else{
        document.querySelector('button').innerText = "Grid View";
           }
    }
  }
}
</script>

<style scoped>
#tweets {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
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
   border: 3px solid black;
}



@media screen and (max-width: 991px) {
  #tweets {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
 }
</style>