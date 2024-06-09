<template>
  <div>
    <section>
      <v-container>
        {{ selectedCategory }}
        <v-select
          label="Select category"
          :items="c.categories.map((category) => category.strCategory)"
          v-model="selectedCategory"
          @update:model-value="changeUrl(selectedCategory)"
        ></v-select>
        <v-row>
          <v-col
            cols="12"
            md="6"
            lg="4"
            v-for="meal in product.meals"
            :key="meal"
          >
          <card :meal="meal"/>
            <!-- <v-card class="pt-19">
              <v-card-title>{{ meal.strMeal }}</v-card-title>
              <v-img
                height="200px"
                :lazy-src="meal.strMealThumb"
                :src="meal.strMealThumb"
                cover
              ></v-img>
            </v-card> -->
            <!-- <card
              :name="'sleep'"
              :image="'https://www.themealdb.com/images/media/meals/vdwloy1713225718.jpg'"
            />  -->
          </v-col>
        </v-row>
      </v-container>
    </section>
  </div>
</template>

<script setup>
// array.forEach(element => {

// });
const selectedCategory = ref("Seafood");
const url = ref("https://www.themealdb.com/api/json/v1/1/filter.php?c=Seafood");

const { data: product } = await useFetch(url);
const { data: c } = await useFetch(
  "https://www.themealdb.com/api/json/v1/1/categories.php"
);
function changeUrl(category) {
  url.value = `https://www.themealdb.com/api/json/v1/1/filter.php?c=${category}`;
}
</script>

<style lang="scss" scoped>
</style>