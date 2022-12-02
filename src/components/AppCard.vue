<script>
export default {
  name: "AppCard",
  props: {
    info: Object,
  },
};
</script>

<template>
  <div class="my-card">
    <img
      class="poster"
      :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`"
      :alt="info.title"
    />

    <h4>
      Titolo: <small>{{ info.title }}</small>
    </h4>
    <h5>
      Titolo originale: <small>{{ info.original_title }}</small>
    </h5>
    <h5>Popularity: {{ info.popularity }}</h5>
    <h5>Original language: {{ info.original_language }}</h5>
    <h1>Vote: {{ info.vote_average }}</h1>
    <!-- <h5>Overview {{ info.overview }}</h5> -->
  </div>
</template>

<style>
img {
  width: 300px;
}

.my-card {
  margin: 10px;
}
</style>
