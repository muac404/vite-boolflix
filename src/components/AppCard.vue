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
    <div class="card-text">
      <h2>
        {{ info.title }}
      </h2>
      <h5>Titolo originale: {{ info.original_title }}</h5>
      <h4>Popularity: {{ info.popularity }}</h4>
      <h4>Original language: {{ info.original_language }}</h4>
      <h1 class="gold">Vote: {{ info.vote_average }}</h1>
      <!-- <h5>Overview {{ info.overview }}</h5> -->
    </div>
  </div>
</template>

<style>
img {
  width: 250px;
  transition: all 1.5s;
}

img:hover {
  filter: grayscale(100);
}

.my-card {
  margin: 10px;
  width: 250px;
  border-radius: 15px;
  cursor: pointer;
  transition: all 0.2s;
}

.my-card:hover {
  background-color: rgba(0, 0, 0, 0.75);
  scale: 1.2;
  box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px,
    rgba(0, 0, 0, 0.22) 0px 15px 12px;
}

.card-text {
  padding: 10px;
  color: #f5f5f1;
}

.gold {
  color: #ffd966;
}
</style>
