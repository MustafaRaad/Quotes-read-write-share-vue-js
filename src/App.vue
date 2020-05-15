<template>
  <div class="container">
    <app-header class="text-center row" :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <new-quote @quoteAdded="newQuote" class="row col-12"></new-quote>
    <quote-grid class="row" v-bind:quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid>
    <div class="row">
      <div class="col-12 text-center">
        <div class="alert alert-info">Info: Click on a quote</div>
        <button @click="modInverse(15,26)">modInverse</button>
        <h1>{{modInverse()}}</h1>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";
import Header from "./components/Header";
export default {
  data() {
    return {
      quotes: ["Mustafa"],
      maxQuotes: 10
    };
  },
  components: {
    QuoteGrid,
    NewQuote,
    appHeader: Header
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Fuck you i said < 10");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    },
    modInverse(a, b) {
      a %= b;
      console.log("a%=b = ", a % b);

      for (var n = 1; n < b; n++) {
        if ((a * n) % b == 1) {
          console.log("n = ", n)
          return n;
        }
        console.log("(a*n)%b = ", (a * n) % b);
      }
    }
  }
};
</script>
