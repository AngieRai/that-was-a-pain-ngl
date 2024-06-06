<template>
  <div>
    <v-card class="pt-19">
      <v-card-title>{{ meal.strMeal }}</v-card-title>
      <v-img
        height="200px"
        :src="meal.strMeal"
        cover
      ></v-img>
    </v-card>
  </div>
</template>

<script setup>
defineProps(["name","image"]);
</script>

<style scoped>
</style>