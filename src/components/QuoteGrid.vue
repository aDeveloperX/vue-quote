<template>
  <div class="row">
    <appQuote
      :key="quote"
      v-for="(quote, index) in quotes"
      @click.native="deleteQuote(index)"
    >{{quote}}</appQuote>
  </div>
</template>

<script>
import Quotes from "./Quote.vue";
export default {
  props: ["quotes"],
  components: {
    appQuote: Quotes,
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    },
  },
};
</script>

<style>
</style>