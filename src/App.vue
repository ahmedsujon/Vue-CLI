<template>
  <div id="app">
    <h2>{{ title }}</h2>
    <navbar></navbar>
    <Allfriends :friends="friends"></Allfriends>
    <Onlinefriend :friends="friends"></Onlinefriend>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Allfriends from "./components/Allfriends.vue";
import Onlinefriend from "./components/Onlinefriend.vue";

export default {
  name: "App",
  data() {
    return {
      title: "Vue Basic Runing :)",
      friends: [
        { name: "A", online: true },
        { name: "B", online: true },
        { name: "C", online: true },
        { name: "D", online: false },
        { name: "E", online: true },
        { name: "F", online: false }
      ]
    };
  },
  components: {
    Navbar,
    Allfriends,
    Onlinefriend
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
