<template>
    <div>
<section class="py-10">
 <v-container>
    <!-- {{meal.meals[0].strMealThumb}} -->
    <v-row>
        <v-col cols="12" md="6">
 <v-img :src="meal.meals[0].strMealThumb" :lazy-src="meal.meals[0].strMealThumb"></v-img> 
        </v-col>
         <v-col cols="12" md="6">
<h1 class="text-h3">{{meal.meals[0].strMeal}}</h1>
<h5 class="pt-10 pb-10 text-h4">Instrusctions</h5>
<p class="text-h5">{{meal.meals[0].strInstructions}}</p>
<a :href="meal.meals[0].strYoutube" target="_blank">Watch on Yt</a>
        </v-col>
    </v-row>
 </v-container>
</section>
    </div>
</template>

<script setup>
const route = useRoute();

const {data: meal} = useFetch(`https://www.themealdb.com/api/json/v1/1/lookup.php?i=${route.params.id}`);
</script>


<style scoped>
a{
    text-decoration: none;
    background-color: red;
    color: white;
    padding: 4px 8px;
    border-radius: 5px
    
}
</style>