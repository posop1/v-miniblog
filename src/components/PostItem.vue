<template>
  <div class="post">
    <div>
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>
    <div class="post_btns">
      <my-button
        @click="$emit('remove', post)"
      >
        Удалить
      </my-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  padding: 25px;
  border: 2px solid whitesmoke;
  border-radius: 10px;
  color: white;
  margin-bottom: 25px;
  font-size: 18px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>