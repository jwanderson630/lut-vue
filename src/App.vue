<template>
  <div id="app">
    <Header title="title"/>
    <MoviesList/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import MoviesList from "./components/MoviesList.vue";
import { setTimeout } from "timers";

export default {
  name: "app",
  data() {
    return {
      title: "Vue Test"
    };
  },
  components: {
    MoviesList,
    Header
  }
};
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
}

*,
*:before,
*:after {
  box-sizing: border-box;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
