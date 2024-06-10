<template>
    <div>
 <section>
      <v-container>
        <h1 class="text-center py-3">Meals</h1>
     <v-text-field label="search meal" variant="outlined" v-model="q" @keyup="changeUrl(q)"></v-text-field>
        <v-row>
          <v-col
            cols="12"
            md="6"
            lg="4"
            v-for="meal in product.meals"
            :key="meal"
          >
          <card :meal="meal"/>
           
          </v-col>
        </v-row>
      </v-container>
    </section>
    </div>
</template>

<script setup>
const q = ref("")
const url = ref("https://www.themealdb.com/api/json/v1/1/search.php?s=");
const {data: product} = await useFetch(url);
function changeUrl(search){
    url.value = `https://www.themealdb.com/api/json/v1/1/search.php?s=${search}`
}
</script>

<style scoped>

</style>