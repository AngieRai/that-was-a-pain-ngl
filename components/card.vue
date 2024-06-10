<template>
  <div>
    <v-card class="pt-19" height="300" hover :to="`/meals/${meal.idMeal}`">
      <v-card-title>{{ meal.strMeal }}</v-card-title>
      <h1>{{meal.idMeal}}</h1>
      <v-img
        height="200"
        :src="meal.strMealThumb" :lazy-src="meal.strMealThumb"
        cover
      ></v-img>
    </v-card>
  </div>
</template>

<script setup>
defineProps(["meal"]);
</script>

<style scoped>
</style>