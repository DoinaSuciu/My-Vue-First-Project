<template>
  <main class="blog-page">
    <h1>Here are my blog posts: </h1>
    <ul>
      <li v-for="post in posts">
      <h2>
        <span>{{ post.id }}.&nbsp;</span>
        <router-link :to="`/post/${post.id}`">{{ post.title }}</router-link>
      </h2>
      </li>
    </ul>
    <button>MORE POSTS</button>
  </main>
</template>

<script>
  import axios from 'axios'

  export default {
    name: 'Blog',
    data () {
      return {
        posts: []
      }
    },
    created () {
      const url = `https://jsonplaceholder.typicode.com/posts`
      axios.get(url)
      .then(resp => {
        this.posts = resp.data
      })
      .catch(e => {
        console.log (e.response ? e.response.data : e)
      })
    }
  }
</script>

<style>
  button {
        display: block;
        align-self: center;
        margin: 50px auto 0;
        color: white;
        background-color: black;
        font-size: 18px;
        min-height: 40px;
        min-width: 100px;
        border: none;
        padding: 12px 24px;
        border-radius: 100px;
        cursor: pointer;
      }
</style>
