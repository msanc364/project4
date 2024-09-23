<template>
    <div class="recipe-list">
      <h2>Recipe List</h2>
      <ul>
        <li v-for="recipe in recipes" :key="recipe.id" @click="selectRecipe(recipe)">
          {{ recipe.name }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RecipeList',
    data() {
      return {
        recipes: [
          { id: 1, name: 'Spaghetti Bolognese' },
          { id: 2, name: 'Chicken Salad' },
          { id: 3, name: 'Vegetarian Pizza' },
        ],
      };
    },
    methods: {
      selectRecipe(recipe) {
        this.$emit('recipe-selected', recipe);
      },
    },
  };
  </script>
  
  <style scoped>
  ul {
    list-style: none;
    padding: 0;
  }
  li {
    cursor: pointer;
    padding: 5px;
  }
  </style>
  