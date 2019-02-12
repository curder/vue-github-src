<template>
  <div>
    <ul>
      <li v-for="post in posts">
        {{ post.id }}: {{ post.title }}
      </li>
    </ul>

  </div>
</template>

<script>
import axios from 'axios';

const url = 'https://jsonplaceholder.typicode.com/posts';

export default {
  name: 'Index',
  data() {
    return {
      posts: [],
    }
  },
  mounted() {
    axios.get(url)
    .then(res => this.posts = res.data.slice(0, 5));
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
