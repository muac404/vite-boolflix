<script>
import axios from "axios";
import AppCard from "./AppCard.vue";
export default {
  name: "AppMain",
  components: {
    AppCard,
  },
  data() {
    return {
      movies: [],
    };
  },
  created() {
    axios
      .get(
        "https://api.themoviedb.org/3/search/movie?api_key=16f73b46f87883610eccec6b3eb8063d&query=matrix"
      )
      .then((risposta) => {
        console.log(risposta.data.results);
        this.movies = risposta.data.results;

        // console.log(this.movies);
      });
  },
};
</script>
<template>
  {{ movies }}
  <AppCard />
</template>

<style></style>
