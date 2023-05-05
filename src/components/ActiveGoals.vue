<template>
  <h1>Active Goals</h1>
  <ul v-for="(activeGoal, index) in activeGoals" :key="index">
    <li>{{ activeGoal }}</li>
  </ul>
</template>
<script>
export default {
  props: {
    activeGoals: Array,
  },
};
</script>
