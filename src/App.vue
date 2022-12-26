 <!-- AIzaSyDcTKNkC3BLz333DLLpgz2f5dqVh-2iz1A  -->
<template>
  <div class="p-8">
    <div>
      {{ meal.strMeal }}
    </div>
    <div>
      {{ meal.strCategory }}
    </div>
    <div>
      {{ meal.strArea }}
    </div>
    <div class="whitespace-pre-line">
      {{ meal.strInstructions }}
    </div>
    <div>
      <div v-show="meal.strIngredient1">
        <p>{{meal.strIngredient1}}</p>
        <p>{{meal.strMeasure1}}</p>
      </div>
      <div v-show="meal.strIngredient2">
        <p>{{meal.strIngredient2}}</p>
        <p>{{meal.strMeasure2}}</p>
      </div>
      <div v-show="meal.strIngredient3">
        <p>{{meal.strIngredient3}}</p>
        <p>{{meal.strMeasure3}}</p>
      </div>
      <div v-show="meal.strIngredient4">
        <p>{{meal.strIngredient4}}</p>
        <p>{{meal.strMeasure4}}</p>
      </div>
      <div v-show="meal.strIngredient5">
        <p>{{meal.strIngredient5}}</p>
        <p>{{meal.strMeasure5}}</p>
      </div>
      <div v-show="meal.strIngredient6">
        <p>{{meal.strIngredient6}}</p>
        <p>{{meal.strMeasure6}}</p>
      </div>
      <div v-show="meal.strIngredien7">
        <p>{{meal.strIngredient7}}</p>
        <p>{{meal.strMeasure7}}</p>
      </div>
      <div v-show="meal.strIngredient8">
        <p>{{meal.strIngredient8}}</p>
        <p>{{meal.strMeasure8}}</p>
      </div>
      <div v-show="meal.strIngredient9">
        <p>{{meal.strIngredient9}}</p>
        <p>{{meal.strMeasure9}}</p>
      </div>
      <div v-show="meal.strIngredient10">
        <p>{{meal.strIngredient10}}</p>
        <p>{{meal.strMeasure10}}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import axios from "axios";

const meal = ref({});

onMounted(() =>
  axios
    .get("https://www.themealdb.com/api/json/v1/1/random.php")
    .then((response) => {
      console.log(response.data.meals[0]);
      meal.value = response.data.meals[0];
    })
);
</script>
<style>
@tailwind base;
@tailwind components;
@tailwind utilities;
</style>
