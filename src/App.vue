<template>
  <div class="container">
    <h1>Meal Finder</h1>
    <Search @search-meal="postResults" @random-meal="postRandom" />
    <ResultsHeading v-if="meals.length" />
    <Results :meals="meals" v-if="meals.length" />
  </div>
</template>

<script>
import Search from './components/Search';
import ResultsHeading from './components/Results-Heading';
import Results from './components/Results';

export default {
  name: 'App',
  components: {
    Search,
    ResultsHeading,
    Results,
  },
  data() {
    return {
      meals: [],
    };
  },
  methods: {
    postResults(meals) {
      this.meals = meals;
    },
    postRandom(meal) {
      this.meals = [meal];
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  background-color: #2d2013;
  color: #fff;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  margin: 0;
}

.container {
  margin: auto;
  max-width: 800px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}
</style>
