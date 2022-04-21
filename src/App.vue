<template>
  <div class="app-header">
    <div class="main-title">
      <div class="title" @click="goHome">thresheld</div>
    </div>

    <div>
      <nav>
        <router-link
          id="nav-info"
          to="/"
          @click="changeBackgroundInfo"
        >
          home
        </router-link> |
        <router-link
          id="nav-watch"
          to="/watch"
          @click="changeBackgroundWatch"
        >
          watch
        </router-link> |
        <router-link
          id="nav-explore"
          to="/explore"
          @click="changeBackgroundExplore"
        >
          explore
        </router-link> |
        <router-link
          id="nav-about"
          to="/about"
          @click="changeBackgroundAbout"
        >
          about
        </router-link> |
        <router-link
          id="nav-further"
          to="/further"
          @click="changeBackgroundFurther"
        >
          further
        </router-link>
      </nav>
    </div>
  </div>

  <router-view />
</template>

<script>
  const bucket = process.env.VUE_APP_BUCKETEER_BUCKET_NAME;

  export default {
    methods: {
      goHome() {
        window.location = '/';
      },
      changeBackgroundInfo() {
        document.getElementById('app').style.background  = `url('https://${bucket}.s3.amazonaws.com/public/landscape_ocean.jpg')`;
        document.getElementById('app').style.backgroundSize  = "cover";

        if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
          document.getElementById('app').style.height = "auto"
        } else {
          document.getElementById('app').style.height = "100vh" ;
        }
      },
      changeBackgroundWatch() {
        document.getElementById('app').style.background  = '#F3C5C5';
        document.getElementById('app').style.backgroundSize  = "cover";

        if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
          document.getElementById('app').style.height = "auto"
        } else {
          document.getElementById('app').style.height = "100vh" ;
        }
      },
      changeBackgroundExplore() {
        // document.getElementById('app').style.background  = `url('https://${bucket}.s3.amazonaws.com/public/swirlclip2.gif')`;
        document.getElementById('app').style.backgroundSize  = "cover";

        if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
          document.getElementById('app').style.height = "auto"
        } else {
          document.getElementById('app').style.height = "auto" ;
        }
      },
      changeBackgroundAbout() {
        document.getElementById('app').style.background  = `url('https://${bucket}.s3.amazonaws.com/public/portrait_ocean_scaled.jpg')`;
        document.getElementById('app').style.backgroundSize  = "cover";


        if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
          document.getElementById('app').style.height = "auto" ;
        } else {
          document.getElementById('app').style.height = "auto" ;
        }
      },
      changeBackgroundFurther() {
        document.getElementById('app').style.background  = '#F3C5C5';
        document.getElementById('app').style.backgroundSize  = "cover";


        if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
          document.getElementById('app').style.height = "auto" ;
        } else {
          document.getElementById('app').style.height = "auto" ;
        }}
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
    color: black;
    font-size: 16px;
    font-weight: 400;
    background-size: cover;
    padding-bottom: 60px;
    font-weight: 200;
  }

  .app-header {
    display: flex;
    flex-wrap: wrap;
    padding: 16px;
    height: 150px;
    align-items: center;
    background: #F3c5c5;
    margin-bottom: 32px;
    opacity: 0.678;
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

  .main-title:hover {
    cursor: pointer;
  }

  /* Small devices (portrait tablets and large phones, 600px and up) */
  @media only screen and (min-width: 600px) {
    .main-title {
      font-size: 115px;
    }
  }

  nav a {
    font-weight: bold;
    color: black;
    text-decoration: none;
    font-size: 0.875em;
  }

  nav a.router-link-exact-active {
    background: chartreuse;
    color: black;
    text-decoration: none;
  }

  .link {
    background: none;
    text-decoration: underline;
    color: black;
  }

  .link:hover {
    background: chartreuse;
    text-decoration: none;
  }

  .content {
    margin: auto 20px;
  }

  .watch.content {
    text-align: center;
  }

  .paragraph,
  .image-container {
    text-align: justify;
    margin-top: 0;
    margin-right: 40px;
    margin-left: 40px;
  }

  /* Extra large devices (large laptops and desktops, 1200px and up) */
  @media only screen and (min-width: 1200px) {
    .paragraph,
    .image-container {
      margin-right: 250px;
      margin-left: 250px;
    }
  }

  .chartreuse {
    font-weight: 500;
    text-align: center;
    background: chartreuse;
    opacity: 0.8;
  }
</style>
