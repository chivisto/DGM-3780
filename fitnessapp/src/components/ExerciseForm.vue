<template>
  <div id="exercise">
    <form @submit.prevent="handleSubmit">

      <label>Running or Bench Press? </label>
      <select v-model="routine.exerciseName">
        <option>Running</option>
        <option>Bench Press</option>
      </select>
      <br><br><br>

      <h3>Running</h3>
      <label>Distance in Miles: </label>
      <input v-model="routine.miles" type="number" />

      <label>Time in Hours: </label>
      <input v-model="routine.hours" type="number" />
      <br><br><br>

      <h3>Bench Press</h3>
      <label>Sets: </label>
      <input v-model="routine.sets" type="number" />

      <label>Reps: </label>
      <input v-model="routine.reps" type="number" />

      <label>Weight in Pounds: </label>
      <input v-model="routine.weight" type="number" />

      <label>Dat: </label>
      <input v-model="routine.date" type="date" />
      <br><br><br>

      <button>Add Exercise</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "exercise",
  data() {
    return {
      routine: {
        exerciseName: "",
        miles: "",
        hours: "",
        sets: "",
        reps: "",
        weight: "",
        date: "",
      },
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("add:routine", this.routine);
      this.routine = {
        exerciseName: "",
        miles: "",
        hours: "",
        sets: "",
        reps: "",
        weight: "",
        date: "",
      };
    },
  },
};
</script>

<style>
form {
  margin-bottom: 5rem;
}
label {
  padding: 7px;
}
button {
  margin: 5px;
}
</style>