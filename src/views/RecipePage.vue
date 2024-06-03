<script setup>
import { onMounted, ref } from 'vue'
import { useRecipeStore } from '@/store/recipeStore'
import RecipeCard from '../components/RecipeCard.vue'
import { storeToRefs } from 'pinia'

const store = useRecipeStore()
const { recipes } = storeToRefs(store)
const count = ref(0)

onMounted(() => {
  store.getAllRecipes()
})
const updateMe = (me) => {
  console.log(me)
  console.log('from child')
  if (!me) {
    count.value++
  } else {
    count.value--
  }
}
</script>
<template>
  <h1>Recipes</h1>
  Count {{ count }}
  <div class="container">
    <div class="row">
      <RecipeCard
        v-for="(recipe, index) in recipes"
        :key="index"
        :recipedetails="recipe"
        @update-favourites="updateMe"
      />
    </div>
  </div>
</template>
