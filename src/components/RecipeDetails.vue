<template>
    <div class="recipe-details" v-if="recipe">
      <h3>{{ recipe.name }}</h3>
      <p>Details about the recipe will go here...</p>
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
  </style>
  