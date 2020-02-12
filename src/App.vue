<template>
  <div class="container">
      <new-quote @quoteAdded="addQuote($event)"></new-quote>
      <quote-grid :quotes="quotes"></quote-grid>
      <div class="row">
          <div class="col-sm-12" text-center>
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
export default {
  data: function() {
    return {
      quotes: ["This is a default quote"],
      maxQuotes: 16
    }
  },
  methods: {
      addQuote: function(quote) {
          this.quotes.push(quote);
      }
  },
  components: {
      quoteGrid: QuoteGrid,
      newQuote: NewQuote
  }
};
</script>

<style>
</style>
