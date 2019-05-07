<template>
  <div class="movie">
    <img :src="getPosterPath" :alt="movie.title">
    <div class="movie_info">
      <h2>{{movie.title}}</h2>
    </div>
  </div>
</template>

<script>
const POSTER_PATH = "https://image.tmdb.org/t/p/w185_and_h278_bestv2";
export default {
  name: "Movie",
  props: ["movie"],
  computed: {
    getPosterPath: function() {
      return `${POSTER_PATH}${this.movie.poster_path}`;
    }
  }
};
</script>

<style lang="scss" scoped>
.movie {
  position: relative;
  overflow: hidden;
  transform: scale(0.95) translateY(0);
  transition: transform 0.2s ease-in-out;
  .movie_info {
    position: absolute;
    top: 0;
    background-color: rgba(0, 0, 0, 0.4);
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
    padding: 10px;
    width: 100%;
    height: 100%;
    overflow: hidden;
    h2 {
      position: absolute;
      bottom: 0;
      font-size: 18px;
      transition: transform 0.2s ease-in-out, opacity 0.3s ease-in-out;
      color: white;
      opacity: 0;
      transform: translateY(100%);
      user-select: none;
    }
  }
  &:hover {
    transform: scale(1) translateY(-2px);
    .movie_info {
      opacity: 1;
      h2 {
        opacity: 1;
        transform: translateY(0);
      }
    }
    img {
      transform: scale(1.1);
    }
  }
}
img {
  box-shadow: 1px 1px 7px 3px rgba(0, 0, 0, 0.5);
  transform: scale(1);
  transition: transform 0.2s ease-in-out;
  width: 100%;
  display: block;
}
</style>