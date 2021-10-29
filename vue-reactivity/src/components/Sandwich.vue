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
          <li v-for="bread in breads" :key="bread">
            <button @click="addIngredient">
              {{ ingredients[0].name }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Meat Options</h3>
        <ul>
          <li v-for="meat in meats" :key="meat">
            <button @click="addIngredient">
              {{ ingredients[1].name }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Veggie Options</h3>
        <ul>
          <li v-for="veggie in veggies" :key="veggie">
            <button @click="addIngredient">
              {{ ingredients[2].name }}
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
      stuff: {
        ingredients: [
        { name: "breads", types: ["Sourdough", "Toast", "Italian"] },
        { name: "meats", types: ["Turkey", "Beef Roast", "Chicken Breast"] },
        { name: "veggies", types: ["Lettuce", "Cucumber", "Tomato"] },
        ]
      },
    };
  },
  
  methods: {
    addIngredient: function (e) {
      this.ingredients.push({
        bread: this.stuff.ingredients[0].types.forEach(),
        meat: this.stuff.ingredients[1].types.forEach(),
        vegg: this.stuff.ingredients[2].types.forEach(),
      });
      e.preventDefault();
    },
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
