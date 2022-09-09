<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/getintouch">Get In Touch</router-link>
  </nav>
  <router-view/>
</template>

<style>
body {
  padding: 0;
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
  background-color: #212529;
  color: #fff;
  font-weight: bold;
}

nav a {
  font-weight: bold;
  color: #fff;
}

nav a:hover {
  color: rgb(194, 194, 194);
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
