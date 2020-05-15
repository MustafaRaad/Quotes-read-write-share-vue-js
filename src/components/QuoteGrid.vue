<template>
  <div class="row jumbotron">
    <app-quote
      class="text-center"
      :key="quote"
      v-for="quote in quotes"
      @click.native="deleteQuote(index)"
    >{{ quote }}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";

export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
};
</script>
