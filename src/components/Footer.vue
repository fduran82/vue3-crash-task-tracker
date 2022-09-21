<template>
    <footer>
      <p>&copy; Copyright - {{currentYear}}</p>
      <router-link to="/about">About</router-link>
    </footer>
  </template>

<script>
    export default {
      data() {
        return {
          currentYear: new Date().getFullYear(), // 2020
        };
      }
    };
</script>
  
<style scoped>
  a {
    color: #333;
  }
  footer {
    margin-top: 30px;
    text-align: center;
  }
</style>