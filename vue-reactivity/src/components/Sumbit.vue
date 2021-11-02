<template>
    <form class="ingredient-list" @submit.prevent="onSubmit">
    
      <p class="error" v-if="errors.length">
        <b>Please correct the following error(s):</b>
        <ul>
          <li v-for="error in errors" :key="error">{{ error }}</li>
        </ul>
      </p>
       <p>
        <input type="submit" value="Submit">  
      </p>
</template>

<script>
/* export default {
     data() {
    return {
      breads: null,
      meats: null,
      veggies: null,
      errors: [],
    };
  },
  methods: {
    onSubmit() {
      if (this.breads && this.meats && this.veggies) {
        let sandwich = {
          breads: this.breads,
          meats: this.meats,
          veggies: this.veggies,
        };
        this.$emit("ingredient-submitted", sandwich);
        this.breads = null;
        this.meats = null;
        this.veggies = null;
      } else {
        if (!this.breads) this.errors.push("Bread required.");
        if (!this.meats) this.errors.push("Meat required.");
        if (!this.veggies) this.errors.push("Veggie required.");
      }
    },
  },
} */
</script>
