<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>

<script> 
import Header from './components/layout/Header';
export default {
  name: "app",
  components: {
    Header
  }

}
</script> 


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: lighter;
  color: #756c83;
}


#nav a.router-link-exact-active {
  color: #fff1c1;
}
</style>
fff1c1