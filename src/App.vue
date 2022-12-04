<template>
  <the-header></the-header>
  <panel-workout></panel-workout>
</template>

<script>
import TheHeader from "./components/layouts/TheHeader.vue";
import PanelWorkout from './components/workouts/PanelWorkout.vue'

export default {
  components: {
    TheHeader,
    PanelWorkout
  },
 
 
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0
}

html {
  font-family: 'Open Sans', sans-serif;
}

body {
  padding: 2rem
}

body {
  background-color: rgb(45, 45, 45);
  color: rgb(208, 208, 208)
}

h1 {
  text-align: center;
  padding-bottom:2rem
}

</style>
