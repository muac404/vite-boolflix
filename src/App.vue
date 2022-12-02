<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";
export default {
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    searchMovie(data = "") {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "16f73b46f87883610eccec6b3eb8063d",
            query: this.store.searchText,
            language: "it-IT",
          },
        })
        .then((risposta) => {
          console.log(this.store);
          this.store.movies = risposta.data.results;
        })
        .catch((err) => {
          this.store.movies = [];
        });
    },
  },
};
</script>

<template>
  <div>
    <AppHeader @search="searchMovie" />
    <div class="main-section">
      <AppMain />
    </div>
    <AppFooter />
  </div>
</template>

<style scoped>
.main-section {
  margin-top: 20px;
}
</style>
