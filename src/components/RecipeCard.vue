<template>
  <!-- Recipe Cardd -->
  <!-- {{ recipedetails }} -->
  <div class="col-md-3">
    <img :src="recipedetails.image" width="100" alt="" />
    {{ updatedName || recipedetails.name }}
    <!-- <button @click="emit('updateFavourites')">Send Item to Parent</button> -->
    <i :class="`${added?'fa-solid':'fa-regular'} text-danger fa-heart`" @click="toggleFave"></i>

    <!-- Button trigger modal -->
    <button
      type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      :data-bs-target="`#exampleModal${recipedetails.id}`"
    >
      Make this
    </button>

    <!-- Modal -->
    <div
      class="modal fade"
      :id="`exampleModal${recipedetails.id}`"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <RecipeModal :recipelist="recipedetails" @update-name-to-parent="updateName"/>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue';
import RecipeModal from './RecipeModal.vue';
defineProps(['recipedetails'])
const emit = defineEmits(['updateFavourites','changeName'])
const added = ref(false)
const toggleFave = ()=>{
  emit('updateFavourites',added.value)
  added.value = !added.value
}
const updatedName = ref('')
const updateName = (name)=>{
  console.log(name)
  updatedName.value = name
}
</script>
