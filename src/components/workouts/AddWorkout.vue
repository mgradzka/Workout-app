<template>
  <base-card>
    <form @submit.prevent="submitForm" class="flex">
      <h2>Add a new workout!</h2>
      <div>
        <label for="name">Type</label>
        <input type="text" name="name" id="name" ref="inputName" />
      </div>
      <!-- <base-button @click="addExercise">Add exercise</base-button> -->
      <div>
        <label for="date">Date</label>
        <input type="date" name="date" id="date" ref="inputDate" />
      </div>
      <div>
        <label for="description">Comments</label>
        <textarea
          type="textarea"
          row="3"
          name="description"
          id="description"
          ref="inputDesc"
        />
      </div>

      <!-- test -->
      <div class="exercise">
        <div>
          <label for="exercise">Core exercise</label>
          <input
            type="text"
            name="exercise"
            id="exercise"
            class="shorter"
            ref="inputEx"
          />
        </div>
        <div>
          <label for="sets">Sets</label>
          <input
            type="text"
            name="sets"
            id="sets"
            class="short-imput"
            ref="inputSets"
          />
        </div>
        <div>
          <label for="series">Series</label>
          <input
            type="text"
            name="series"
            id="series"
            class="short-imput"
            ref="inputSeries"
          />
        </div>
      </div>

      <!-- test -->

      <warning-msg v-if="invalidInput">Try to fill out all fields!</warning-msg>
      <div class="btn-container"><base-button>Submit</base-button></div>
    </form>
  </base-card>
</template>

<script>
import WarningMsg from "../UI/BaseMessage.vue";
// import AddExercise from "./AddExercise.vue";
export default {
  components: {
    WarningMsg,
    // AddExercise,
  },
  data() {
    return {
      invalidInput: false,
      buttonClicked: false,
    };
  },
  inject: ["submitData"],
  methods: {
    submitForm() {
      const enteredName = this.$refs.inputName.value;
      const enteredDate = this.$refs.inputDate.value;
      const enteredDesc = this.$refs.inputDesc.value;

      const enteredEx = this.$refs.inputEx.value;
      const enteredSets = this.$refs.inputSets.value;
      const enteredSeries = this.$refs.inputSeries.value;

      if (
        enteredName === "" ||
        enteredDate === "" ||
        enteredDesc === "" ||
        enteredEx === "" ||
        enteredSets === "" ||
        enteredSeries === ""
      ) {
        this.invalidInput = true;
        return;
      }

      this.submitData(
        enteredName,
        enteredDate,
        enteredDesc,
        enteredEx,
        enteredSets,
        enteredSeries
      );
    },
    addExercise() {
      return (this.buttonClicked = true);
    },
  },
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  background-color: rgb(181, 181, 181);
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.2rem;
  border: 1px solid rgb(181, 181, 181);
}

.flex {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.exercise {
  display: flex;
  gap: 2rem;
}

</style>
