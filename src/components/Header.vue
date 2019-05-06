<template>
  <header>
    <h1>{{title}}</h1>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    title: String
  }
};
</script>

<style lang="scss" scoped>
header {
  background-color: #111;
  color: #fff;
  padding: 20px;
  text-align: center;
}
</style>