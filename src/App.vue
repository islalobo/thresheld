<template>
  <div class="app-header">
    <div class="logo" @click="goHome">
      thresheld
    </div>

    <div class="nav-area">
      <nav>
        <router-link to="/">info</router-link> |
        <router-link to="/watch">watch</router-link> |
        <router-link to="/explore">explore</router-link> |
        <router-link to="/about">about</router-link>
      </nav>
    </div>
  </div>

  <router-view />
</template>

<script>
const goHome = async () => {
  console.log('click');
}
</script>

<style>
  body {
    margin: 0px;
  }

  #app {
    font-family: "Montserrat", sans-serif;
    text-align: center;
    color: white;
    background-color: black;
    height: 100vh;
  }

  .app-header {
    display: flex;
    flex-wrap: wrap;
    padding: 20px;
    height: 50px;
    align-items: center;
  }

  .nav-area {
    flex: 1;
    text-align: end;
    position: relative;
  }

  .logo {
    flex: 1;
    text-align: start;
    font-size: 34px;
    position: relative;
  }

  nav a {
    font-weight: bold;
    color: white;
  }

  nav a.router-link-exact-active {
    color: #42b983;
  }
</style>
