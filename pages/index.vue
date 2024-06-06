<template>
  <div>
    <section>
      <v-container>
        <v-row>
          <v-col
            cols="12"
            md="6"
            lg="4"
            v-for="meal in product.meals"
            :key="meal"
          >
            <v-card class="pt-19">
              <v-card-title>{{ meal.strMeal }}</v-card-title>
              <v-img height="200px" :src="meal.strMealThumb" cover></v-img>
            </v-card>
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
const { data: product } = useFetch(
  "https://www.themealdb.com/api/json/v1/1/filter.php?c=Seafood"
);
</script>

<style lang="scss" scoped>
</style>