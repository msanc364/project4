<template>
    <div class="recipe-details" v-if="recipe">
      <h3>{{ recipe.name }}</h3>
      <ul>
        <li v-for="ingredient in recipe.ingredients" :key="ingredient.name">
          {{ ingredient.name }} - {{ ingredient.amount }} {{ ingredient.unit }}
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
  