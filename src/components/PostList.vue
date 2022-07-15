<template>
  <div v-if="posts.length > 0">
    <post-item 
      :key="post.id" 
      v-for="post in posts" 
      :post="post" 
      @remove="$emit('remove', post)"
    />
  </div>
  <h2 v-else>
    Список пуст
  </h2>
</template>

<script>
import PostItem from "./PostItem.vue";

export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
h2{
  font-size: 28px;
  text-align: center;
}
</style>