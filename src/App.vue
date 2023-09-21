<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/projects">Projects</router-link> |
    <router-link to="/add">Add Project</router-link> |
    <router-link to="/edit">Edit Project</router-link> |
  </nav>
  <router-view/>
</template>

<style>
body{
  background-color: #f2f2f2;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  max-width: 600px;
  margin: 0 auto;
  color: #555;
}

</style>
