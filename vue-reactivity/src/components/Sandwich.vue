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
            <button @click="addBread">
              {{ bread }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Meat Options</h3>
        <ul>
          <li v-for="meat in meats" :key="meat">
            <button @click="addMeat">
              {{ meat }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Veggie Options</h3>
        <ul>
          <li v-for="veggie in veggies" :key="veggie">
            <button @click="addVeggie">
              {{ veggie }}
            </button>
          </li>
        </ul>
      </div>
      <h3>Order</h3>
      <ul>
        <li v-for="item in order" :key="item"></li>
      </ul>
    </div>
    <!-- <Submit @ingredient-submitted="addIngredient"></Submit> -->
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
      breads: ["Sourdough", "Toast", "Italian"],
      meats: ["Turkey", "Beef Roast", "Chicken Breast"],
      veggies: ["Lettuce", "Cucumber", "Tomato"],
      order: [{bread:""}, {meat:""}, {veggie:""}],
  };
  },
  methods: {
     addBread() {
       let orderBread = order[0].bread;
       this.breads.push(orderBread);
      },  
     addMeat() {
       let orderMeat = order[1].meat;
       this.meats.push(orderMeat);
      },  
     addVeggie() {
       let orderVeggie = order[2].veggie;
       this.veggies.push(orderVeggie);
      },  

  },
};
//console.log(this.ingredients[2].types[0]);
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
