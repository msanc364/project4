<template>
    <div class="recipe-details" v-if="recipe">
      <h3>{{ recipe.name }}</h3>
      <ul>
        <li v-for="(ingredient, index) in recipe.ingredients" :key="index">
        {{ ingredient.name }} - {{ ingredient.amount }} {{ ingredient.unit }} 
        - Cost: ${{ ingredient.cost.toFixed(2) }} 
        - Calories: {{ ingredient.calories }} kcal
      </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RecipeDetails',
    props: ['recipe'],
  };
  </script>
  
  <style scoped>
  h3 {
    margin-top: 0;
  }
  ul {
    list-style: none;
    padding: 0;
  }
  li {
    padding: 5px;
  }
  </style>
  