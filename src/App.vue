<template>
  <div class="app">
    <div class="container inner">
      <h1>Страница с постами</h1>
      <my-button class="createPost" @click='openDialog'>Создать пост</my-button>
      <my-dialog v-model:open='dialogVisible'>
        <post-form 
          @create='createPost'
        />
      </my-dialog>
      <post-list 
        :posts="posts"
        @remove="removePost"
      />
    </div>
  </div>
</template>

<script>
import PostForm from './components/PostForm'
import PostList from './components/PostList'

export default {
  components: {
    PostForm,
    PostList
  },

  data() {
    return {
      posts: [
        {id: 1, title: 'Пост о JS', body: 'JavaScript мультипарадигменный язык'},
        {id: 2, title: 'Пост о JS 2', body: 'JavaScript мультипарадигменный язык'},
        {id: 3, title: 'Пост о JS 3', body: 'JavaScript мультипарадигменный язык'},
        {id: 4, title: 'Пост о JS 4', body: 'JavaScript мультипарадигменный язык'},
        {id: 5, title: 'Пост о JS 5', body: 'JavaScript мультипарадигменный язык'},
        {id: 6, title: 'Пост о JS 6', body: 'JavaScript мультипарадигменный язык'}
      ],
      dialogVisible: false,
    }
  },

  methods: {
    createPost(post){
      this.posts.push(post)
      this.dialogVisible = false
    },
    removePost(post){
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    openDialog() {
      this.dialogVisible = true
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
  h1{
    font-size: 45px;
    margin: 30px 0;
  }
  .createPost{
    margin-bottom: 30px;
  }
</style>