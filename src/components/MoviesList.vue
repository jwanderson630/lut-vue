<template>
  <ul>
    <li :key="movie.id" v-for="movie in movies">
      <Movie :movie="movie"/>
    </li>
  </ul>
</template>

<script>
import Movie from "./Movie.vue";

export default {
  name: "MoviesList",
  data() {
    return {
      movies: []
    };
  },
  methods: {
    fetchData: async function() {
      const data = await fetch(
        "https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=df8b87a4741a82e0f95d79a719efe70c"
      )
        .then(d => d.json())
        .catch(error => error);
      this.movies = data.results;
    }
  },
  created: function() {
    this.fetchData();
  },
  components: {
    Movie
  }
};
</script>

<style lang="scss" scoped>
</style>