<template>
  <div id="exercise-table">
    <table>
      <thead>
        <tr>
          <th>exercise</th>
          <th>miles</th>
          <th>hours</th>
          <th>sets</th>
          <th>reps</th>
          <th>weight</th>
          <th>dat</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="routine in routines" :key="routine.id">
          <td>
            {{ routine.exerciseName }}
          </td>

          <td>
            {{ routine.miles }}
          </td>

          <td>
            {{ routine.hours }}
          </td>

          <td>
            {{ routine.sets }}
          </td>

          <td>
            {{ routine.reps }}
          </td>

          <td>
            {{ routine.weight }}
          </td>

          <td>
            {{ routine.date }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "exercise-list",
  props: {
    routines: Array,
  }
};
</script>

<style scoped>
th {
  padding: 10px;
  padding-left: 50px;
  padding-right: 50px;
}
td {
  padding: 5px;
  color: rgb(25, 85, 25);
  border-top: black 1px solid;
  padding-bottom: 2rem;
}
button {
  margin-left: 3px;
}
table {
  margin: 0 auto;
  border: solid 1px black;
}
</style>