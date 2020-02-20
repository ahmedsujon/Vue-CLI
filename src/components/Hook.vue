<template>
  <h1>Hook</h1>
</template>

<script>
export default {
  name: "Hook",
  data() {
    return {};
  },
  beforeCreate() {
    alert("Before Created Hook");
  },
  mounted() {
    alert("Created Hook");
  }
};
</script>

<style scoped>
</style>