<template>
  <div id="allfriends">
    <h2>All Friends</h2>
    <div v-for="(friend, index) in friends" :key="index">
      <span>{{ friend.name }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Allfriends",
  props: ["friends"],
  data() {
    return {};
  }
};
</script>

<style scoped>
nav {
  text-align: center;
}
nav ul {
  padding: 0;
}
nav li {
  display: inline-block;
  list-style-type: none;
  margin: 0;
  padding: 8px;
}
</style>