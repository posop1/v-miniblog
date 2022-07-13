<template>
  <div class="app">
    <div class="container inner">
      <form @submit.prevent>
        <h4>Создание поста</h4>
        <input 
          v-model="title" 
          class="input" 
          type="text" 
          placeholder="Введите название поста."
        >
        <input 
          v-model="body" 
          class="input" 
          type="text" 
          placeholder="Введите описание поста."
        >
        <button @click="createPost">Создать пост</button>
      </form>
      <div class="post" v-for="post in posts" v-bind:key = 'post.id'>
        <div><strong>Название:</strong>  {{ post.title }}</div>
        <div><strong>Описание:</strong> {{ post.body }}</div>
      </div>  
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      body: '',
      posts: [
        {id: 1, title: 'Пост о JS', body: 'JavaScript мультипарадигменный язык'},
        {id: 2, title: 'Пост о JS 2', body: 'JavaScript мультипарадигменный язык'},
        {id: 3, title: 'Пост о JS 3', body: 'JavaScript мультипарадигменный язык'},
        {id: 4, title: 'Пост о JS 4', body: 'JavaScript мультипарадигменный язык'},
        {id: 5, title: 'Пост о JS 5', body: 'JavaScript мультипарадигменный язык'},
        {id: 6, title: 'Пост о JS 6', body: 'JavaScript мультипарадигменный язык'}
      ]
    }
  },
  methods: {
    createPost(){
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body 
      }
      this.posts.push(newPost)
      this.title = ''
      this.body = ''
    }
  }
}
</script>

<style>
  html, body, div, span, applet, object, iframe,
  h1, h2, h3, h4, h5, h6, p, blockquote, pre,
  a, abbr, acronym, address, big, cite, code,
  del, dfn, em, img, ins, kbd, q, s, samp,
  small, strike, sub, sup, tt, var,
  b, u, i, center,
  dl, dt, dd, ol, ul, li,
  fieldset, form, label, legend,
  table, caption, tbody, tfoot, thead, tr, th, td,
  article, aside, canvas, details, embed, 
  figure, figcaption, footer, header, hgroup, 
  menu, nav, output, ruby, section, summary,
  time, mark, audio, video {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font-family: 'Roboto', sans-serif;
    vertical-align: baseline;
    color: white;
  }
  /* HTML5 display-role reset for older browsers */
  article, aside, details, figcaption, figure, 
  footer, header, hgroup, menu, nav, section {
    display: block;
  }
  body {
    line-height: 1;
    background: rgba(0, 0, 0, 0.89);
    box-sizing: border-box;
  }
  ol, ul {
    list-style: none;
  }
  blockquote, q {
    quotes: none;
  }
  blockquote:before, blockquote:after,
  q:before, q:after {
    content: '';
    content: none;
  }
  table {
    border-collapse: collapse;
    border-spacing: 0;
  }


  .container{
    max-width: 1200px;
    margin: 0 auto;
  }
  .inner{
    display: flex;
    flex-direction: column;
  }
  .post{
    padding: 15px;
    border: 2px solid whitesmoke;
    border-radius: 10px;
    color: white;
    margin-bottom: 25px;
    font-size: 18px;
  }
  form{
    display: flex;
    flex-direction: column;
    padding: 15px;
    border: 2px solid whitesmoke;
    border-radius: 10px;
    margin: 50px 0px;
  }
  form h4{
    font-size: 24px;
    margin-bottom: 20px;
  }
  .input{
    max-width: 400px;
    outline: none;
    border: none;
    margin-bottom: 15px;
    padding: 8px;
    font-size: 14px;
    background: whitesmoke;
    font-family: 'Roboto', sans-serif;
    border-radius: 2px;
  }
  button{
    font-family: 'Roboto', sans-serif;
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
  button:hover{
    background: rgba(255, 255, 255, 0.13);
    color: white;
  }
</style>