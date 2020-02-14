<template>
  <div class="container">
      <header-quote :quoteCount="quotes.length" :maxQuotes="maxQuotes"></header-quote>
      <new-quote @quoteAdded="addQuote($event)"></new-quote>
      <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote($event)"></quote-grid>
      <div class="row">
          <div class="col-sm-12" style="textAlign: center">
              <div class="alert alert-info">
                  Info: Click on a Quote to delete it!
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: ["This is a default quote"],
      maxQuotes: 16,
    }
  },
  methods: {
      addQuote: function(quote) {
          if(this.quotes.length >= this.maxQuotes) {
            return alert('Please delete a quote first');
          } else if (quote.length == 0) {
            return alert('Please enter your quote before click');
          }
          this.quotes.push(quote);
      },
      deleteQuote: function(index) {
          this.quotes.splice(index, 1);
      }
  },
  components: {
      quoteGrid: QuoteGrid,
      newQuote: NewQuote,
      headerQuote: Header,
  }
};
</script>

<style>
</style>
