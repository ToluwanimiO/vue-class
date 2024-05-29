<script setup>
import { onMounted } from 'vue'
import { useRecipeStore } from '@/store/recipeStore'
import RecipeCard from '../components/RecipeCard.vue'
import { storeToRefs } from 'pinia'

const store = useRecipeStore()
const { recipes } = storeToRefs(store)

onMounted(() => {
  store.getAllRecipes()
})
</script>
<template>
  <h1>Recipes</h1>
  <div class="container">
    <div class="row">
        <RecipeCard v-for="(recipe, index) in recipes" :key="index" :recipedetails="recipe"/>
    </div>
  </div>
</template>
