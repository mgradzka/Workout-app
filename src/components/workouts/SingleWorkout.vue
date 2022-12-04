<template>
  <article>
    <base-card>
      <div class="flex">
        <h2>{{ workout.name }}</h2>
        <base-button @click="deleteWorkout(id)" mode="transparent"
          >Delete</base-button
        >
      </div>
      
      <the-exercise
      v-for="exercise in workout.exercises"
        :title="exercise.title"
        :key="exercise.id"
      :sets="exercise.sets"
      :series="exercise.series"></the-exercise>
      <p><strong>Date:</strong> {{ workout.date }}</p>
      <p><strong>Note:</strong> {{ workout.description }}</p>
    </base-card>
  </article>
</template>

<script>
import TheExercise from './TheExercise.vue'
export default {
  props: ["workout", "id"],
  inject: ["deleteWorkout"],
  components: {
TheExercise
  }
};
</script>

<style scoped>
.flex {
  display: flex;
  justify-content: space-between;
}
</style>
