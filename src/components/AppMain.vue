<script>
import axios from "axios";
import AppCard from "./AppCard.vue";

export default {
  name: "AppMain",
  components: {
    AppCard,
  },
  data() {
    return {};
  },
  created() {
    axios
      .get(
        "https://api.themoviedb.org/3/movie/550?api_key=16f73b46f87883610eccec6b3eb8063d"
      )
      .then((risposta) => {
        console.log(risposta.data);
        this.personaggi = risposta.data;
      });
  },
};
</script>

<template>
  <!-- <section class="container">
    <select name="" id="">
      <option selected>Select category</option>
      <option value="">Breaking Bad</option>
      <option value="">Better Call Saul</option>
    </select>
    <div class="container-cards">
      <div class="founds">
        <h4>Found 62 characters</h4>
      </div>
      <div class="row">
        <div class="col"></div>
      </div>
    </div>
  </section> -->
</template>

<style></style>
