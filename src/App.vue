<script>
import { store } from "./store";
import axios from "axios";

import AppMain from "./components/AppMain.vue";

export default {
  components: {
    AppMain,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    saluta(data) {},
  },
  created() {
    axios
      .get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: "e99307154c6dfb0b4750f6603256716d",
        },
      })
      .then((response) => {
        this.store.movies = response.data.results;
      });
  },
};
</script>

<template>
  <div>
    <AppMain />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
