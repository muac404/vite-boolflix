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
    <h1>METHFLIX</h1>

    <form @click="$emit('search')">
      <input
        type="text"
        placeholder="Es. Star Wars"
        v-model="store.searchText"
        required
      />
      <button class="src-btn" type="submit">SEARCH</button>
    </form>
  </header>
</template>

<style scoped>
header {
  height: 120px;
  background-color: #eaeaea;
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  /* position: fixed;
  left: 0;
  right: 0;
  left: 0;
  z-index: 999; */
}
input {
  padding: 10px;
  min-width: 250px;
  margin-right: 10px;
}
h1 {
  color: #e50914;
  margin-right: 40px;
}

.src-btn {
  padding: 10px 20px;
  color: #eaeaea;
  background-color: #e50914;
  border: none;
  cursor: pointer;
}

.src-btn:hover {
  background-color: #221f1f;
}
</style>
