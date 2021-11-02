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
          <li v-for="bread in ingredients" :key="bread">
            <button @click="addIngredient">
              {{ ingredients[0].types[0] }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Meat Options</h3>
        <ul>
          <li v-for="meat in ingredients" :key="meat">
            <button @click="addIngredient">
              {{ breads[1] }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Veggie Options</h3>
        <ul>
          <li v-for="veggie in ingredients" :key="veggie">
            <button @click="addIngredient">
              {{ ingredients[2].types[0] }}
            </button>
          </li>
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
      ingredients: [
        { name: "breads", types: ["Sourdough", "Toast", "Italian"] },
        { name: "meats", types: ["Turkey", "Beef Roast", "Chicken Breast"] },
        { name: "veggies", types: ["Lettuce", "Cucumber", "Tomato"] },
      ],
      breads: ["Sourdough", "Toast", "Italian"],
    };
  },

  methods: {
    addIngredient: function (e) {
      this.ingredients.push({
        bread: this.ingredients[0].types.forEach(),
        meat: this.ingredients[1].types.forEach(),
        vegg: this.ingredients[2].types.forEach(),
      });
      e.preventDefault();
    },
  },
};
console.log(this.ingredients[2].types[0]);
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

ul {
  list-style-type: none;
  //padding: 0;
  // display: flex;
  //flex-direction: column;
  //}
  //li {
  // //display: inline-block;
  // margin: 0 10px;
  //display: flex;
  // flex-direction: column;
}
</style>
