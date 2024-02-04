<template>
  <div>
    <!-- primo video -->
    <div class="video-background">
      <video autoplay muted loop id="video-background1" class="filter-video">
        <source
          src="/src/assets/images/Isometric Apps Development Background video _ Footage _ Screensaver.mp4"
          type="video/mp4"
        />
        Il tuo browser non supporta il tag video.
      </video>
      <div class="content content-overlay">
        <div
          class="d-flex justify-content-center align-items-center align-content-center h-100"
        >
          <div class="container h-100">
            <div class="row h-100">
              <div
                class="col-8 d-flex justify-content-center flex-column text-center text-light"
              >
                <h2 class="display-5 fw-semibold">Giulia Mariano</h2>
                <h1 class="display-1">MyPortfolio</h1>
                <h3 class="display-5">webdeveloper</h3>
              </div>
              <div class="col d-flex align-items-center">
                <div class="profile-picture overflow-hidden">
                  <img
                    src="/src/assets/images/Mee.png"
                    alt="my-image"
                    class="w-100"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- sfondo-colore -->
    <div class="video-background color-1">
      <div class="content content-overlay">
        <div id="background-wrap">
          <div class="bubble x1"></div>
          <div class="bubble x2"></div>
          <div class="bubble x3"></div>
          <div class="bubble x4"></div>
          <div class="bubble x5"></div>
          <div class="bubble x6"></div>
          <div class="bubble x7"></div>
          <div class="bubble x8"></div>
          <div class="bubble x9"></div>
          <div class="bubble x10"></div>
        </div>
        <div class="h-100 container">
          <div class="row w-100 d-flex justify-content-center align-content-center align-items-center  h-100 ">
            <div class="col-4">
                <h2 class="text-light display-4 fw-medium   ">
            Tecnologie con cui lavoro
          </h2>
            </div>
            <div class="col-5">
              
          <div class="d-flex flex-wrap  mt-5 w-100 h-100">
            <div class="d-flex flex-wrap ">
              <div
                v-for="technology in store.technologies"
                :key="technology.id"
                class="my-icon m-4"
              >
                <img
                  :src="`${store.imgPath}image/${technology.name}.png`"
                  :alt="technology.name"
                  class="d-block w-100 "
                  :class="{
                    'invert-img':
                      technology.name === 'GitHub' || technology.name === 'PHP',
                  }"
                />
                 <span class="name-icon d-flex justify-content-center ">{{ technology.name }}</span>
              </div>
            </div>
          </div>
            </div>
          </div>
        
        </div>
      </div>
    </div>

    <!-- secondo video -->
    <div class="video-background">
      <video autoplay muted loop id="video-background2" class="filter-video">
        <source
          src="/src/assets/images/Hud Futuristic Interface Background video _ Footage _ Screensaver.mp4"
          type="video/mp4"
        />
      </video>
      <div class="content content-overlay">
        <div
          class=" h-100"
        >
        <h2 class="text-light py-5 text-center display-4">Sono una sviluppatrice <span class="fw-medium">FullStack</span></h2> 
        <div class="div-1 border-fluid">
          <h3>Frontend</h3>
          <p>
            sono in grado si sviluppare pagine lato frontend, utilizzando linguaggi come html, css e javascript. Utilizzo vue.js e bootstrap
          </p>
        </div>
        <div class="div-2 border-fluid">
          <h3>Backend</h3>
          <p>
            sono in grado si sviluppare anche pagine lato backend utilizzando linguaggio php su Larvale
          </p>
        </div>
         
        </div>
      </div>
    </div>

    <!-- sfondo-colore -->
    <div class="video-background color-1">
      <div class="content content-overlay">
        <div
          class="d-flex justify-content-center align-items-center align-content-center h-100"
        >
          <h1 class="text-light">Ciao</h1>
        </div>
      </div>
    </div>

    <!-- terzo video -->
    <div class="video-background">
      <video autoplay muted loop id="video-background3" class="filter-video">
        <source
          src="/src/assets/images/Graph Background video _ Footage _ Screensaver.mp4"
          type="video/mp4"
        />
        Il tuo browser non supporta il tag video.
      </video>
      <div class="content content-overlay">
        <div
          class="d-flex justify-content-center align-items-center align-content-center h-100"
        >
          <h1 class="text-light">Ciao</h1>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { store } from "../store.js";
import axios from "axios";

export default {
  name: "AppHome",

  data() {
    return {
      store,
      currentPage: 1,
      totalPages: 0,
    };
  },
  methods: {
    getAllTechnologies() {
      axios.get(this.store.apiUrl + "technologies").then((res) => {
        console.log(res.data);
        this.store.technologies = res.data.results;
      });
    },
  },
  created() {
    this.getAllTechnologies();
  },
};
</script>
<style lang="scss" scoped>
@use "../assets/style/partials/bubble" as *;
@use "../assets/style//partials/borderfluid" as *;
.video-background {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

.filter-video {
  filter: grayscale(20%) brightness(50%);
}

#video-background1,
#video-background2,
#video-background3 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.color-1 {
  background: rgb(34, 15, 73);
  background: linear-gradient(
    200deg,
    rgba(34, 15, 73, 1) 27%,
    rgba(15, 7, 39, 1) 57%,
    rgba(2, 1, 12, 1) 100%
  );
}

.content {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  color: white;

  .col-8 {
    h1,
    h2,
    h3 {
      text-shadow: 0px 0px 20px black;
    }
  }
}
.profile-picture {
  width: 400px;
  height: 400px;
  border-radius: 50%;
  border: 8px solid rgba(64, 43, 142, 0.59);
  -webkit-box-shadow: 0px 0px 186px 27px rgba(64, 43, 142, 0.59);
  -moz-box-shadow: 0px 0px 186px 27px rgba(64, 43, 142, 0.59);
  box-shadow: 0px 0px 186px 27px rgba(64, 43, 142, 0.59);
}
.content-overlay {
  background: rgba(0, 0, 0, 0.3); /* Aggiungi una sfumatura in overlay */
}
.invert-img {
  filter: invert(1);
}
div{
  .my-icon{
    transition: 0.5s;
    z-index: 2;
  }
  .my-icon:hover {
    transform: scale(1.4);
    cursor: pointer;

    .name-icon{
      opacity: 1;
    }
  }

  .name-icon{
    opacity: 0;
    transition: 0.5s;
  }

  .div-1{
    background-color:rgb(34, 15, 73);
    width: 30%;
    position: absolute;
    top: 30%;
    left: 10%;
    padding: 60px;
  }

  .div-2{
    background-color: rgba(0, 0, 0, 0.5);
    width: 30%;
    position: absolute;
    bottom: 30%;
    right: 10%;
    padding: 60px;
    z-index: 2;
  }

}
</style>
