<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
export default {
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    searchMovie(data = "") {
      axios
        .get("https://api.themoviedb.org/3/movie", {
          params: {
            api_key: "16f73b46f87883610eccec6b3eb8063d",
            // query: this.store.searchText,
            language: "it-IT",
          },
        })
        .then((risposta) => {
          console.log(this.store);
          this.store.movies = risposta.data.results;
        })
        .catch((err) => {
          this.store.movies = [];
          this.store.series = [];
        });
      if (data === "reset") {
        this.store.searchText = "";
      }
    },
  },
};
</script>

<template>
  <div>
    <AppHeader />
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
