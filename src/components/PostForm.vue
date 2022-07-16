<template>
  <form @submit.prevent>
        <h4>Создание поста</h4>
        <my-input 
          v-model="post.title" 
          type="text" 
          placeholder="Введите название поста."
        />
        <my-input 
          v-model="post.body" 
          type="text" 
          placeholder="Введите описание поста."
        />
        <my-button class="btn" @click="createPost">Создать пост</my-button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                title: '',
                body: ''
            }
        }
    },
    
    methods: {
        createPost() {
            this.post.id = Date.now()
            this.$emit('create', this.post)
            this.post = {
                title: '',
                body: ''
            }
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
        flex-direction: column;
        padding: 15px;
        border: 2px solid whitesmoke;
        border-radius: 10px;
    }
    form h4{
        font-size: 24px;
        margin-bottom: 20px;
        color: black;
    }
    .btn{
        align-self: flex-end;
    }
    
</style>