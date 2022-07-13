<template>
  <button>
    <slot></slot>
  </button>
</template>

<script>
export default {
    name: 'my-button'
};
</script>

<style scoped>
button {
  font-family: "Roboto", sans-serif;
  max-width: 200px;
  border: none;
  outline: none;
  background: white;
  cursor: pointer;
  font-size: 16px;
  padding: 8px;
  border-radius: 10px;
  transition: 0.3s;
}
button:hover {
  background: rgba(255, 255, 255, 0.13);
  color: white;
}
</style>