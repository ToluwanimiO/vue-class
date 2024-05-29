<script setup>
  const user = {
    id:'123',
    name:'Tope'
  }
</script>

<template>
  <RouterLink :to="{name:'home'}">Go to Home</RouterLink>
  <RouterLink to="/about">Go to About</RouterLink>
  <RouterLink :to="`/user/${user.name}`">Go to User</RouterLink>
  <RouterLink to="/recipes" >Go to Recipes</RouterLink>
  <RouterView/>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
