<template>
  <h1>Manage Goals</h1>
  <input type="text" ref="inputGoal" v-model="goal" />
  <button @click="setGoal">Set Goal</button>
  <Teleport to="body">
    <ErrorAlert v-if="inputIsInvalid">
      <p>please input something!</p>
      <button @click="dialogClose">ok</button>
    </ErrorAlert>
  </Teleport>
</template>
<script>
import ErrorAlert from "../components/ErrorAlert.vue";

export default {
  data() {
    return {
      goal: "",
      inputIsInvalid: false,
    };
  },
  props: {
    activeGoals: Array,
  },
  emits: ["addToActiveGoals"],
  components: {
    ErrorAlert,
  },
  methods: {
    setGoal() {
      if (this.goal === "") {
        this.inputIsInvalid = true;
      } else {
        this.$emit("addToActiveGoals", this.goal);
      }
      this.goal = "";
    },
    dialogClose() {
      this.inputIsInvalid = false;
    },
  },
};
</script>
<style scoped>
button {
  color: #fff;
  background: green;
}
</style>
