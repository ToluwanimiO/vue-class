<template>
    This is our Home Page
    <HomeDetails >
        <template #tope>
            <p>More details about Home</p>
            <p>For more questions, go to FAQ</p>
        </template>
        <template v-slot:mary="maryProps">
            <p>Mary's details</p>
            {{ maryProps.message }}
        </template>
    </HomeDetails>
</template>
<script setup>
import HomeDetails from "../components/HomeDetails.vue"
</script>
