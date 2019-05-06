<template>
  <img :src="getPosterPath" :alt="movie.title">
</template>

<script>
export default {
  name: "Movie",
  props: ["movie"],
  computed: {
    getPosterPath: function() {
      return `https://image.tmdb.org/t/p/w185_and_h278_bestv2${
        this.movie.poster_path
      }`;
    }
  }
};
</script>

<style lang="scss" scoped>
</style>