<template>
  <section>
    <single-workout
      v-for="workout in workouts"
      :key="workout.id"
      :id="workout.id"
      :workout="workout"
    
    >
      ></single-workout
    >
  </section>
</template>
<script>
import SingleWorkout from "./SingleWorkout.vue";

export default {
  components: {
    SingleWorkout,
  },
  data() {
    return {};
  },
  inject: ["workouts"],
};
</script>

<style scoped></style>
