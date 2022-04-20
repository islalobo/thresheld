<template>
  <div class="app-header">
    <div
      class="main-title"
      @click="goHome"
    >
      thresheld
    </div>

    <div class="nav-area">
      <nav>
        <router-link
          to="/"
          @click="changeBackgroundInfo"
        >
          info
        </router-link> |
        <router-link
          to="/watch"
          @click="changeBackgroundWatch"
        >
          watch
        </router-link> |
        <router-link
          :id="explore"
          to="/explore"
          @click="changeBackgroundExplore"
        >
          explore
        </router-link> |
        <router-link
          to="/about"
          @click="changeBackgroundAbout"
        >
          about
        </router-link>
      </nav>
    </div>
  </div>

  <router-view />
</template>

<script>
  export default {
    methods: {
      goHome() {
        window.location = '/';
      },
      changeBackgroundInfo() {
        document.getElementById('app').style.background  = "url('../pinkwater.gif')";
        document.getElementById('app').style.backgroundSize  = "cover";
        // navigator.userAgentData.mobile
        //   ? document.getElementById('app').style.height = "auto"
        //   : document.getElementById('app').style.height = "100vh" ;
        // document.getElementById('app').style.color = "ghostwhite";
      },
      changeBackgroundWatch() {
        document.getElementById('app').style.background  = "black";
        document.getElementById('app').style.backgroundSize  = "cover";
        // navigator.userAgentData.mobile
        //   ? document.getElementById('app').style.height = "auto"
        //   : document.getElementById('app').style.height = "100vh" ;
        // document.getElementById('app').style.color = "ghostwhite";
      },
      changeBackgroundExplore() {
        document.getElementById('app').style.background  = "url('../swirlclip2.gif')";
        document.getElementById('app').style.backgroundSize  = "cover";
        // navigator.userAgentData.mobile
        //   ? document.getElementById('app').style.height = "auto"
        //   : document.getElementById('app').style.height = "100vh" ;
        // document.getElementById('app').style.color = "black";
      },
      changeBackgroundAbout() {
        document.getElementById('app').style.background  = "url('../pinkwater.gif')";
        document.getElementById('app').style.backgroundSize  = "cover";
        // navigator.userAgentData.mobile
        //   ? document.getElementById('app').style.height = "auto"
        //   : document.getElementById('app').style.height = "100vh" ;
        // document.getElementById('app').style.color = "ghostwhite";
      },
    }
  }
</script>

<style>
  body {
    margin: 0px;
    height: auto;
  }

  #app {
    font-family: "Montserrat", sans-serif;
    text-align: justify;
    color: ghostwhite;
    font-size: 16px;
    font-weight: 400;
    background-size: cover;
    padding-bottom: 60px;
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
    font-size: .875em;
  }

  .main-title {
    flex: 1;
    text-align: start;
    font-size: 72px;
    position: relative;
  }

  /* Small devices (portrait tablets and large phones, 600px and up) */
  @media only screen and (min-width: 600px) {
    .main-title {
      font-size: 115px;
    }
  }

  nav a {
    font-weight: bold;
    color: ghostwhite;
    text-decoration: none;
  }

  nav a.router-link-exact-active {
    background: chartreuse;
    color: black;
    text-decoration: none;
  }

  .content {
    margin: auto 20px;
  }

  .watch.content {
    text-align: center;
  }

  .paragraph {
    text-align: justify;
    margin: auto 40;
    padding-top: 20px;
    position: relative;
  }

  /* Extra small devices (phones, 600px and down) */
  /* @media only screen and (max-width: 600px) {
    .paragraph {
      margin: auto 150px;
    }
  } */

  /* Extra large devices (large laptops and desktops, 1200px and up) */
  @media only screen and (min-width: 1200px) {
    .paragraph {
      margin: auto 250px;
    }
  }

  .chartreuse {
    color: chartreuse;
    font-weight: bold;
    font-size: 20px;
    text-align: center;
  }
</style>
