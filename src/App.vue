<template>
  <div id="app">
    <Random @change="change" />
    <Quote v-if="control==true"  @handleLook="handleLook" :msg="message" />
    <Quotes v-else :msgLook="msgLook" />
    <footer>muhsin61@DevChallenge.io</footer>
  </div>
</template>

<script>
import Quote from  './components/Quote.vue'
import Quotes from './components/Quotes.vue'
import Random from './components/Random.vue'

export default {
  name: 'App',
  components: {
    Quote,
    Quotes,
    Random
  },
  created: function() {
    this.change();
    },
  data() {
    return {
      message: {quote:"",author:"",quoteGenre:""},
      msgLook : null,
      control: true,
      authorName: "Bill%20Gates"
    };
  },
  methods: {
    change(){
      fetch("https://quote-garden.herokuapp.com/api/v2/quotes/random")
        .then(response => response.json())
        .then(data => {
          console.log(data.quote.quoteText);
          console.log(data.quote.quoteAuthor);
          this.message.quote = data.quote.quoteText;
          this.message.author = data.quote.quoteAuthor;
          this.message.quoteGenre = data.quote.quoteGenre;
        }) 
        .catch(err => console.log(err));
        this.control=true;
      },
      handleLook(){
        this.authorName = this.message.author.replace(" ","%20")
        fetch("https://quote-garden.herokuapp.com/api/v2/authors/"+this.authorName+"?page=1&limit=10")
        .then(response => response.json())
        .then(data => {
        console.log(data);
        this.msgLook = data.quotes;
        console.log(this.msgLook)
        this.control= false;
        }) 
        .catch(err => console.log(err));
        
      },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
footer{
  font-family: Montserrat;
  font-style: normal;
  font-weight: 600;
  font-size: 18px;
  line-height: 17px;
}

</style>
