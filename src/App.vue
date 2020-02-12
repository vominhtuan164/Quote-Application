<template>
  <div class="container">
      <quote-grid :quotes="quotes"></quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";

export default {
  data: function() {
    return {
      quotes: ["This is a default quote"],
      maxQuotes: 16
    }
  },
  components: {
      quoteGrid: QuoteGrid,
  }
};
</script>

<style>
</style>
