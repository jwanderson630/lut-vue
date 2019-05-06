<template>
  <div id="app">
    <Header v-bind:title="reverseTitle"/>
    <p>{{hello}}</p>
    <ul>
      <li :key="index" v-for="(item, index) in list">{{index + 1}}. {{ item}}</li>
    </ul>
    <div :key="person.name" v-for="person in people">
      <ul>
        <li :key="`${person.name}'s ${value}'`" v-for="(value, key) in person">{{key}}: {{value}}</li>
      </ul>
    </div>
    <div>
      <label>Is True?</label>
      <input type="checkbox" v-model="isTrue">
    </div>
    <div v-if="loading">Loading...</div>
    <img v-else-if="isTrue && !loading" src="./assets/logo.png" alt="logo">
    <div v-else>It is not true ☹️</div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import { setTimeout } from "timers";

export default {
  name: "app",
  data() {
    return {
      hello: "Hello!",
      title: "Vue Test",
      list: ["Dog", "Cat", "Fish", "Bird"],
      people: [{ name: "Joe", age: "26" }, { name: "Lindsay", age: "25" }],
      isTrue: false,
      loading: true,
      name: "Joe"
    };
  },
  computed: {
    reverseTitle: function() {
      return this.isTrue
        ? this.title
        : this.title
            .split("")
            .reverse()
            .join("");
    }
  },
  created: function() {
    setTimeout(() => (this.loading = false), 2000);
  },
  components: {
    HelloWorld,
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
