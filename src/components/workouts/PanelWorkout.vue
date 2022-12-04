<template>
  <div>
    <base-button @click="chosenTab('all-workouts')">Your workouts</base-button>
    <base-button @click="chosenTab('add-workout')">Add workout</base-button>
  </div>
  <component :is="activeTemplate"></component>

  <p v-if="isEmpty && activeTemplate === 'all-workouts'">
    There are no workouts yet. Add a new one!
  </p>
</template>

<script>
import AllWorkouts from "./AllWorkouts.vue";
import AddWorkout from "./AddWorkout.vue";

export default {
  data() {
    return {
      isEmpty: false,
      activeTemplate: "all-workouts",
      workouts: [
        {
          id: "first-one",
          name: "Upper body workout",
          exercises: [
            {
              id: "Pull-Up",
              title: "Pull Up",
              sets: "3",
              series: "10",
            },
          ],
          date: "2022-12-02",
          description: "Good overall, but i was feeling quite tired. Need to rest more.",
        },
        {
          id: "second-one",
          name: "Lower body workout",
          exercises: [
            {
              id: "squat",
              title: "Squat",
              sets: "4",
              series: "8",
            },
          ],
          date: "2022-11-30",
          description: "It was a GREAT workout!",
        },
      ],
    };
  },

  provide() {
    return {
      submitData: this.submitData,
      workouts: this.workouts,
      deleteWorkout: this.deleteWorkout,
    };
  },
  components: {
    AllWorkouts,
    AddWorkout,
  },
  methods: {
    chosenTab(tab) {
      this.activeTemplate = tab;
    },
    submitData(name, date, desc, ex, sets, series) {
      const newWorkout = {
        id: new Date().toISOString(),
        name: name,
        date: date,
        description: desc,
        exercises: [
          {
            id: new Date().toISOString(),
            title: ex,
            sets: sets,
            series: series,
          },
        ],
      };
      this.workouts.unshift(newWorkout);
      this.activeTemplate = "all-workouts";
        this.isEmpty = false;
      
    },
    deleteWorkout(workoutId) {
      const toBeDeleted = this.workouts.findIndex(
        (workout) => workout.id === workoutId
      );
      this.workouts.splice(toBeDeleted, 1);

      if (this.workouts.length === 0) {
        this.isEmpty = true;
      }
    },
  },
};
</script>
<style scoped>
div {
  margin: 2rem auto;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
}
p {
  text-align: center;
}
</style>
