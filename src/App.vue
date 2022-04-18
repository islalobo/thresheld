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

<style>
  body {
    margin: 0px;
    height: auto;
  }

  #app {
    font-family: "Montserrat", sans-serif;
    text-align: justify;
    color: black;
    background-color: #F3C5C5;
    padding-bottom: 80px;
  }

  .app-header {
    display: flex;
    flex-wrap: wrap;
    padding: 20px;
    height: 150px;
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
    font-size: 72px;
    position: relative;
  }

  /* Small devices (portrait tablets and large phones, 600px and up) */
  @media only screen and (min-width: 600px) {
    .logo {
      font-size: 115px;
    }
  }

  nav a {
    font-weight: bold;
    color: black;
  }

  nav a.router-link-exact-active {
    color: #42b983;
  }

  .content {
    height: 100%;
    margin: auto 20px;
  }

  .watch.content {
    height: 100vh;
  }

  .paragraph {
    text-align: justify;
    margin: auto 40;
    padding-top: 20px;
    position: relative;
  }

  /* Small devices (portrait tablets and large phones, 600px and up) */
  @media only screen and (min-width: 600px) {
    .paragraph {
      margin: auto 150px;
    }
  }

  /* Extra large devices (large laptops and desktops, 1200px and up) */
  @media only screen and (min-width: 1200px) {
    .paragraph {
      margin: auto 250px;
    }
  }
</style>
