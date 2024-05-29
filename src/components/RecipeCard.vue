<template>
  <!-- Recipe Cardd -->
  <!-- {{ recipedetails }} -->
  <div class="col-md-3">
    <img :src="recipedetails.image" width="100" alt="" />
    <!-- Button trigger modal -->
    <button
      type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      Make this
    </button>

    <!-- Modal -->
    <div
      class="modal fade"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <RecipeModal/>
    </div>
  </div>
</template>
<script setup>
import RecipeModal from './RecipeModal.vue';
defineProps(['recipedetails'])
</script>
