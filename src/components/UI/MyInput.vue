<template>
  <input :value="modelValue" @input="updateInput" class="input" type="text" />
</template>

<script>
export default {
  name: "my-input",
  props: {
    modelValue: [String, Number]
  },

  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
};
</script>

<style scoped>
.input {
  max-width: 400px;
  outline: none;
  border: none;
  margin-bottom: 15px;
  padding: 8px;
  font-size: 14px;
  background: whitesmoke;
  font-family: "Roboto", sans-serif;
  border-radius: 2px;
}
</style>