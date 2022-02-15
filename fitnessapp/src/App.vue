<template>
<img src="../src/assets/running.png">
<h1>Exercise App</h1>
  <exerciseForm @add:routine='addRoutine' />
  <exercise :routines='exerciseDone' />
</template>

<script>
import exercise from './components/Exercise.vue'
import exerciseForm from './components/ExerciseForm.vue'

export default {
  name: 'App',
  components: {
    exercise,
    exerciseForm
  },
  data() {
    return {
      exerciseDone: [
      ]
    }
  },
  methods: {
    addRoutine (routine) {
      const newEntry = this.exerciseDone.length > 0
      ? this.exerciseDone[this.exerciseDone.length -1].id
      : 0;
      const entry = newEntry + 1;
      const newRoutines= { ...routine, entry}
      this.exerciseDone = [ ...this.exerciseDone, newRoutines]
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body{
  margin: 0 auto;
  display: flex;
  justify-content: center;
  color: rgb(25, 85, 25);
}
img{
  width: 200px;
  height: 200px;
}
</style>