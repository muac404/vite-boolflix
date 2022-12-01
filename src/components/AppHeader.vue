<script>
import { store } from "../store.js";
export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <header>
    <h1>BOOLFLIX</h1>
    <form @submit.prevent="$emit('search')">
      <input type="text" placeholder="Cerca il tuo film" />
      <button type="submit">Cerca</button>
    </form>
  </header>
</template>

<style></style>
