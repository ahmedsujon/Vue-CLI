<template>
  <div class="Hook">
    <h1>All Posts</h1>
    <input type="text" v-model="searchTerm" placeholder="search" />
    <div v-for="post in filtersearch" :key="post.id">
      <h3>{{ post.id }}</h3>
      <h3>{{ post.title }}</h3>
      <p>{{ post.body | snippet }}</p>
      <hr />
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Hook",
  data() {
    return {
      posts: [],
      searchTerm: ""
    };
  },
  computed: {
    filtersearch() {
      return this.posts.filter(post => {
        return post.title.match(this.searchTerm);
      });
    }
  },

  methods: {},
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/posts")
      .then(response => {
        //console.log(response);
        this.posts = response.data;
      })
      .catch(error => {
        console.log(error);
      });
  }
};
</script>

<style>
h1 {
  color: gray;
  text-align: center;
}
</style>
