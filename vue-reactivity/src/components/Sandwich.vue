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
          <li v-for="(bread,index) in breads" :key="index">
            <button @click="addBread(index)">
              {{ bread }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Meat Options</h3>
        <ul>
          <li v-for="(meat,index) in meats" :key="index">
            <button @click="addMeat(index)">
              {{ meat }}
            </button>
          </li>
        </ul>
      </div>
      <div class="column">
        <h3>Veggie Options</h3>
        <ul>
          <li v-for="(veggie,index) in veggies" :key="index">
            <button @click="addVeggie(index)">
              {{ veggie }}
            </button>
          </li>
        </ul>
      </div>
      <div>
        <h3>Order</h3>
        <ul>
          <li v-for="(item,index) in order" :key="index">{{item}}</li>
          <button type="submit" value="Submit" @click="onSubmit(index)" @submit.prevent="onSubmit(index)">Submit Order</button>
        </ul>
        
      </div>
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
      errors:[],
  };
  },
  methods: {
     addBread(index) {
       let orderBread = {newBreads: this.breads[index]}
       this.order.push(orderBread.newBreads);
      },  
     addMeat(index) {
       let orderMeat = {newMeats: this.meats[index]}
       this.order.push(orderMeat.newMeats);
      },  
     addVeggie(index) {
       let orderVeggie = {newVeggies: this.veggies[index]}
       this.order.push(orderVeggie.newVeggies);
      },  
     onSubmit(index) {
        if (this.breads[index] && this.meats[index] && this.veggies[index]) {
        let sandwichOrder = {
          order: this.order[index],
          /* newBreads: this.breads[index],
          newMeats: this.meats[index],
          newVeggies: this.veggies[index], */
        };
        this.$emit("order-submitted", sandwichOrder);
        this.order[index] = null;
        /* this.breads[index] = null;
        this.meats[index] = null;
        this.veggies[index] = null; */
      } else {
        if (!this.breads[index]) this.errors.push("Bread required.");
        if (!this.meats[index]) this.errors.push("Meat required.");
        if (!this.veggies[index]) this.errors.push("Veggie required.");
      }
    },
  },

  }
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
