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
          <li v-for="(bread,id) in breads" :key="id">
            <button @click="addBread">
              {{ bread }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Meat Options</h3>
        <ul>
          <li v-for="(meat,id) in meats" :key="id">
            <button @click="addMeat">
              {{ meat }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Veggie Options</h3>
        <ul>
          <li v-for="(veggie,id) in veggies" :key="id">
            <button @click="addVeggie">
              {{ veggie }}
            </button>
          </li>
        </ul>
      </div>
      <h3>Order</h3>
      <ul>
        <li v-for="(item,id) in order" :key="id">{{item}}</li>
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
      //order: [{bread:""}, {meat:""}, {veggie:""}],
      order:[],
      newBreads: null,
      newMeats: null,
      newVeggies: null,
  };
  },
  methods: {
     addBread() {
       let orderBread = {newBreads: this.breads[0]}
       this.order.push(orderBread.newBreads);
      },  
     addMeat() {
       let orderMeat = {newMeats: this.meats[0]}
       this.order.push(orderMeat.newMeats);
      },  
     addVeggie() {
       let orderVeggie = {newVeggies: this.veggies[0]}
       this.order.push(orderVeggie.newVeggies);
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
