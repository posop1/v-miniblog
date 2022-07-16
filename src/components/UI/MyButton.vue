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
  border: 1px solid black;
  cursor: pointer;
  font-size: 16px;
  padding: 8px;
  border-radius: 10px;
  transition: 0.3s;
}
button:hover {
  box-shadow: 0 2px 5px rgba(0,0,0,0.2), 0 4px 6px rgba(0,0,0,0.2);
  background: rgba(255, 255, 255, 0.5);
}
</style>