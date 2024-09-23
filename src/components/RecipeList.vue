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
    name: 'STC RecipeList',
    data() {
      return {
        recipes: [
          { 
            id: 1, 
            name: 'Spaghetti Bolognese', 
            ingredients: [
              { name: 'Pasta', amount: 200, unit: 'g', cost: 1.5, calories: 700 },
              { name: 'Ground Beef', amount: 150, unit: 'g', cost: 4, calories: 500 },
              { name: 'Tomato Sauce', amount: 100, unit: 'ml', cost: 2, calories: 80 }
            ]
          },
          { 
            id: 2, 
            name: 'Chicken Salad', 
            ingredients: [
              { name: 'Chicken Breast', amount: 200, unit: 'g', cost: 3, calories: 400 },
              { name: 'Lettuce', amount: 50, unit: 'g', cost: 0.5, calories: 15 },
              { name: 'Olive Oil', amount: 10, unit: 'ml', cost: 0.2, calories: 90 }
            ]
          },
          { 
            id: 3, 
            name: 'Vegetarian Pizza', 
            ingredients: [
              { name: 'Pizza Dough', amount: 250, unit: 'g', cost: 3, calories: 800 },
              { name: 'Cheese', amount: 100, unit: 'g', cost: 2.5, calories: 400 },
              { name: 'Vegetables', amount: 100, unit: 'g', cost: 1, calories: 150 }
            ]
          },
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
  