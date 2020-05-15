<template>
  <div class="container justify-content-center">
    <div class="row">
      <div class="col-12 form-group">
        <label>Quote</label>
        <textarea rows="3" cols="50" class="form-control" v-on:keyup.enter="createNew" v-model="quote"></textarea>
      </div>
      <div class="col-12">
        <button class="btn btn-primary btn-block" @click.prevent="createNew">Add Quote</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew() {
      if (this.quote.length > 0) {
        this.$emit("quoteAdded", this.quote);
      }
      this.quote = "";
    }
  }
};
</script>
