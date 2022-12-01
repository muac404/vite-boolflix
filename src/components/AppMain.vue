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
        "https://api.themoviedb.org/3/movie/550?api_key=16f73b46f87883610eccec6b3eb8063d"
      )
      .then((risposta) => {
        console.log(risposta.data);
        this.movies = risposta.data;
        this.title = risposta.data.title;
        this.originalTitle = risposta.data.original_title;
        this.lang = risposta.data.original_language;
        this.averageVote = risposta.data.vote_average;
        console.log(
          this.movies,
          this.title,
          this.originalTitle,
          this.lang,
          this.averageVote
        );
      });
  },
};
</script>
<template>
  <AppCard />
</template>

<style></style>
