<template>
    <div class="recipe-cost" v-if="recipe">
      <h3>Calculate Recipe Cost</h3>
      <p>Total Cost: ${{ totalCost.toFixed(2) }}</p>
      <p>Total Calories: {{ totalCalories }} kcal</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RecipeCostCalculator',
    props: ['recipe'],
    computed: {
      totalCost() {
        return this.recipe.ingredients.reduce((sum, ingredient) => sum + ingredient.cost, 0);
      },
      totalCalories() {
        return this.recipe.ingredients.reduce((sum, ingredient) => sum + ingredient.calories, 0);
      },
    },
  };
  </script>
  
  <style scoped>
  h3 {
    margin-bottom: 0;
  }
  </style>
  