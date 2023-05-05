<template>
  <dialog open>
    <slot></slot>
  </dialog>
</template>

<style scoped>
dialog {
  position: fixed;
  top: 20vh;
  left: 30%;
  width: 40%;
  background: #fff;
  padding: 1rem;
  box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.5);
}
</style>
