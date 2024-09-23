<template>
  <div id="app">
    <RecipeList @recipe-selected="selectedRecipe = $event" />
    <RecipeDetails :recipe="selectedRecipe" />
    <RecipeCostCalculator />
  </div>
</template>

<script>
import RecipeList from './components/RecipeList.vue';
import RecipeDetails from './components/RecipeDetails.vue';
import RecipeCostCalculator from './components/RecipeCostCalculator.vue';

export default {
  name: 'App',
  components: {
    RecipeList,
    RecipeDetails,
    RecipeCostCalculator,
  },
  data() {
    return {
      selectedRecipe: null,
    };
  },
};
</script>

<style>
#app {
  display: flex;
  gap: 20px;
}
</style>
