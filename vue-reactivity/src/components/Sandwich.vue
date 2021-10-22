<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Choose your bread, protein, and veggies, as well as any other toppings.
    </p>
    <div class="column">
      <h3>Installed CLI Plugins</h3>
      <ul>
        <li>
          <a
            href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint"
            target="_blank"
            rel="noopener"
            >eslint</a
          >
        </li>
      </ul>
    </div>
    <div class="column">
      <h3>Essential Links</h3>
      <ul>
        <li>
          <a href="https://vuejs.org" target="_blank" rel="noopener"
            >Core Docs</a
          >
        </li>
        <li>
          <a href="https://forum.vuejs.org" target="_blank" rel="noopener"
            >Forum</a
          >
        </li>
        <li>
          <a href="https://chat.vuejs.org" target="_blank" rel="noopener"
            >Community Chat</a
          >
        </li>
        <li>
          <a href="https://twitter.com/vuejs" target="_blank" rel="noopener"
            >Twitter</a
          >
        </li>
        <li>
          <a href="https://news.vuejs.org" target="_blank" rel="noopener"
            >News</a
          >
        </li>
      </ul>
    </div>
    <div class="column">
      <h3>Ecosystem</h3>
      <ul>
        <li>
          <a href="https://router.vuejs.org" target="_blank" rel="noopener"
            >vue-router</a
          >
        </li>
        <li>
          <a href="https://vuex.vuejs.org" target="_blank" rel="noopener"
            >vuex</a
          >
        </li>
        <li>
          <a
            href="https://github.com/vuejs/vue-devtools#vue-devtools"
            target="_blank"
            rel="noopener"
            >vue-devtools</a
          >
        </li>
        <li>
          <a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener"
            >vue-loader</a
          >
        </li>
        <li>
          <a
            href="https://github.com/vuejs/awesome-vue"
            target="_blank"
            rel="noopener"
            >awesome-vue</a
          >
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sandwich",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
  //display: flex;
  //flex-direction: column;
}
.column {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  flex-direction: column;
}
li {
  //display: inline-block;
  margin: 0 10px;
  display: flex;
  flex-direction: column;
}
a {
  color: #42b983;
}
</style>
