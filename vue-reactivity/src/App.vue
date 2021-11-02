<template>
  <div id="app">
    <img id="pic" alt="Sandwich picture" src="./assets/sandwiches.jpg" />
    <Sandwich msg="Make your Sandwich!" />
  </div>
</template>

<script>
import Sandwich from "./components/Sandwich.vue";

export default {
  name: "App",
  components: {
    Sandwich,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  //color: #2c3e50;
  //margin-top: 60px;
  background-color: rgb(211, 211, 250);
}
#pic{
  margin-top: 60px;
}
</style>
