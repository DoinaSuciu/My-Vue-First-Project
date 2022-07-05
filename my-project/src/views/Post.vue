<template>
  <main class="post-page">
    <h1>{{ post.title }}</h1>
    <p>{{ post.body }}</p>
    <div class="back-to-blog">
      <router-link to="/blog">Back to Blog</router-link>
    </div>
  </main>
</template>

<script>
  import axios from 'axios'

  export default {
    name: 'Post',
    data () {
      return {
        post: {}
      }
    },
    created() {
      const url = `https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`
      axios.get(url)
      .then(resp => {
        this.post = resp.data
      })
      .catch(e => {
        console.log (e.response ? e.response.data : e)
      })
    }
  }
</script>

<style>
  .back-to-blog {
    margin-top: 25px;
  }
</style>
