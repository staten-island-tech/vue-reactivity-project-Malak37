<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Choose your bread, protein, and veggies, as well as any other toppings.
    </p>
    <div class="row">
      <div class="column">
        <h3>Bread Options</h3>
        <ul>
          <li :v-for="item in items">{{ items.type }}</li>
        </ul>
      </div>
      <div class="column">
        <h3>Bread Options</h3>
        <ul>
          <li :v-for="item in items">{{ items.type }}</li>
        </ul>
      </div>
      <div class="column">
        <h3>Bread Options</h3>
        <ul>
          <li :v-for="item in items">{{ items.type }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sandwich",
  props: {
    msg: String,
  },
  data() {
    return {
      items: [{ type: "Sourdough" }, { type: "Toast" }, { type: "Italian" }],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
//h3 {
//margin: 40px 0 0;
//display: flex;
//flex-direction: column;
//}
.row {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
}

//ul {
//list-style-type: none;
//padding: 0;
// display: flex;
//flex-direction: column;
//}
//li {
// //display: inline-block;
// margin: 0 10px;
//display: flex;
// flex-direction: column;
//}
</style>
