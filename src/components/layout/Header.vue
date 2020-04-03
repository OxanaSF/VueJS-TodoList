<template>
  <header class="header">
    <div id="nav">
      <router-link to="/" class="home">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <h1>Todo List</h1>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
  .header {
    background: #a4c5c6;
    color: #ffeb99;
    font-size: 20px;
    font-family: Arial, Helvetica, sans-serif;
    font-weight: lighter;
    text-align: center;
    padding: 10px;
  }

  #nav {
    text-align: left;
  }

 
  

</style>