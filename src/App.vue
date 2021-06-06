<template>
  <div id="app" >
    <div class="container my-5">
      <div class="row d-flex justify-content-center mb-5">
        <Header :quoteCount="quotesArr.length" :maxQuotes="maxQuotes"></Header>
      </div>
      <div class="row d-flex justify-content-center mb-5">
        <NewQuote @quoteAdded="quoteAddFunc"></NewQuote>
      </div>

      <QuoteGrid :quotes="quotesArr" @quoteDeleted="removeQuote"></QuoteGrid>
      
      <div class="row mt-4">
        <div class="col-12">
          <div class="alert alert-info" role="alert">
            Info : Click Quote to Remove
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue';
  import NewQuote from './components/NewQuote.vue';
  import Header from './components/Header.vue';

  export default {
    data(){
      return {
        quotesArr: ['Knowing is not enough we must go. Willing is not enough we must do'],
        maxQuotes: 10
      }
    },
    methods: {
      quoteAddFunc(quote){
        if(this.quotes.length >= this.maxQuotes){
          return alert('Please delete quotes first');
        }
        this.quotesArr.push(quote);
      },
      removeQuote(index){
        this.quotesArr.splice(index, 1);
      }
    },
    components: {
      QuoteGrid,
      NewQuote,
      Header
    }
  }
</script>


<style>
#app {
  font-family: 'Arizonia, cursive';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
