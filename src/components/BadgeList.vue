<template>
  <section>
    <h2>Available Badges</h2>
    <ul>
      <li>
        <BaseBadge type="admin" caption="ADMIN" />
      </li>
      <li>
        <BaseBadge type="author" caption="AUTHOR" />
      </li>
    </ul>
  </section>
</template>

<script>
import BaseBadge from "./BaseBadge.vue";
export default {
  components: {
    BaseBadge,
  },
};
</script>

<style>
section h2 {
  margin: 0.5rem 0;
  color: #3a3a3a;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
}

li {
  margin-right: 1rem;
}
</style>
