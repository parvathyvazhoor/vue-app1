<template>
  <div>
    <TheHeader />
    <BadgeList />
    <UserInfo
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    />
    <button @click="setSelectedComponent('active-goals')">ActiveGoals</button>
    <button @click="setSelectedComponent('manage-gaols')">ManageGaols</button>
    <KeepAlive>
      <component
        :is="selectedComponent"
        :activeGoals="activeGoals"
        @addToActiveGoals="addToActiveGoals"
      />
    </KeepAlive>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import BadgeList from "./components/BadgeList.vue";
import UserInfo from "./components/UserInfo.vue";
import ActiveGoals from "./components/ActiveGoals.vue";
import ManageGaols from "./components/ManageGaols.vue";

export default {
  data() {
    return {
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
      selectedComponent: "",
      activeGoals: [],
    };
  },
  components: {
    TheHeader,
    BadgeList,
    UserInfo,
    ActiveGoals,
    ManageGaols,
  },
  methods: {
    setSelectedComponent(cmp) {
      return (this.selectedComponent = cmp);
    },
    addToActiveGoals(goal) {
      this.activeGoals.push(goal);
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}
button {
  font-family: inherit;
  color: #000;
  padding: 1rem 2rem;
  outline: none;
  border: 1px solid currentColor;
}
input {
  padding: 1rem;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
