<template>
  <div>
    <AppHero />
    <!-- tecnologie -->
    <div id="technologies" class="background color-1 ">
      <div class="content content-overlay">
        <div class="h-100">
          <div
            class="row w-100 d-flex justify-content-center align-content-center align-items-center flex-column"
          >
            <div class="col m-5 text-center">
              <h2 class="text-light display-4 mt-5">
                <span class="fw-medium">Tecnologie</span> con cui lavoro
              </h2>
              <div v-if="store.technologies.length === 0">
                Nessuna tecnologia trovata.
              </div>
            </div>
            <div class="col w-100 mt-5">
              <div class="w-100">
                <!-- contenitore icone -->
                <div class="d-flex my-icon-container">
                  <!-- singole icone -->
                  <div
                    v-for="technology in store.technologies"
                    :key="technology.id"
                    class="my-icon"
                  >
                    <img
                      :src="`${technology.url_logo}`"
                      :alt="technology.name"
                      class="d-block w-100"
                      :class="{
                        'invert-img':
                          technology.name === 'GitHub' ||
                          technology.name === 'PHP',
                      }"
                    />
                    <span
                      class="name-icon d-flex justify-content-center fst-italic"
                      >{{ technology.name }}</span
                    >
                  </div>

                  <div
                    v-for="technology in store.technologies"
                    :key="technology.id"
                    class="my-icon"
                  >
                    <img
                      :src="`${technology.url_logo}`"
                      :alt="technology.name"
                      class="d-block w-100"
                      :class="{
                        'invert-img':
                          technology.name === 'GitHub' ||
                          technology.name === 'PHP',
                      }"
                    />
                    <span
                      class="name-icon d-flex justify-content-center fst-italic"
                      >{{ technology.name }}</span
                    >
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!--fullstack -->
    <div class="background-fullstack color-2">
      <div class="content content-overlay">
        <div class="h-100">
          <h2 class="text-light py-5 text-center display-4">
            Sono una sviluppatrice <span class="fw-medium">FullStack</span>
          </h2>
          <div class="div-1 border-fluid">
            <h3>Frontend</h3>
            <p>
              sono in grado si sviluppare pagine lato frontend, utilizzando
              linguaggi come html, css e javascript. Utilizzo vue.js e bootstrap
            </p>
          </div>
          <div class="div-2 border-fluid">
            <h3>Backend</h3>
            <p>
              sono in grado si sviluppare anche pagine lato backend utilizzando
              linguaggio php con Larval come Framework
            </p>
          </div>
        </div>
      </div>
    </div>

    <!-- progetti -->
    <div id="projects" class="background2 color-3">
      <div>
        <div
          class="content content-overlay d-flex justify-content-center flex-column"
        >
        <h2 class="display-4 text-center pb-5 text-light">Progetti</h2>
          <div
            class="d-flex flex-column align-items-center align-content-center justify-content-center px-3 container-projects"
          >
            <div
              v-for="post in store.posts"
              :key="post.id"
              class="container p-3"
            >
              <!-- <newCards :post="post"></newCards>  -->
              <router-link
                :to="{ name: 'single-post', params: { slug: post.slug || '' } }"
                class="text-light text-decoration-none"
              >
                <div
                  class="d-flex flex-wrap  justify-content-between px-5 py-3 project"
                >
                  <h3>{{ post.name }}</h3>
                  <span
                    class="text-center d-flex align-items-center align-content-center justify-content-center"
                  >
                    {{
                      post.description.length > 255
                        ? post.description.substring(0, 255) + "..."
                        : post.description
                    }}</span
                  >
                </div>
              </router-link>
            </div>
          </div>
          <!-- <div
          class="d-flex flex-column align-items-center align-content-center card-container"
        >
          <div v-for="post in store.posts" :key="post.id">
            <AppCardsAnimation :post="post"></AppCardsAnimation>
          </div>
         -->
        </div>
      </div>
    </div>

    <!-- github -->
    <div class="background color-4">
      <div id="contacts">
      <video autoplay muted loop id="video-background3" class="filter-video">
        <source
          src="/src/assets/images/Graph Background video _ Footage _ Screensaver.mp4"
          type="video/mp4"
        />
        Il tuo browser non supporta il tag video.
      </video>
      <div class="content content-overlay">
        <div
          class="d-flex justify-content-center align-items-center flex-column align-content-center h-100"
        >
          <h2 class="display-3 px-5">Scopri di più sui miei progetti e su di me</h2>
          <!-- github link -->
          <a
            href="https://github.com/giuliamari04"
            class="text-light text-decoration-none fs-1 d-flex py-3 text-git"
          >
            <div class="icon">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 496 512">
                <path
                  d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3 .3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5 .3-6.2 2.3zm44.2-1.7c-2.9 .7-4.9 2.6-4.6 4.9 .3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3 .7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3 .3 2.9 2.3 3.9 1.6 1 3.6 .7 4.3-.7 .7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3 .7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3 .7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z"
                />
              </svg>
            </div>
            github.com/giuliamari04
          </a>
          <!-- linkedin link -->
          <a
            href="https://www.linkedin.com/in/giulia-mariano-3a1a052b1"
            class="text-light text-decoration-none fs-1 d-flex py-3 text-git"
          >
            <div class="icon">
              <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="100" height="100" viewBox="0 0 50 50">
    <path d="M41,4H9C6.24,4,4,6.24,4,9v32c0,2.76,2.24,5,5,5h32c2.76,0,5-2.24,5-5V9C46,6.24,43.76,4,41,4z M17,20v19h-6V20H17z M11,14.47c0-1.4,1.2-2.47,3-2.47s2.93,1.07,3,2.47c0,1.4-1.12,2.53-3,2.53C12.2,17,11,15.87,11,14.47z M39,39h-6c0,0,0-9.26,0-10 c0-2-1-4-3.5-4.04h-0.08C27,24.96,26,27.02,26,29c0,0.91,0,10,0,10h-6V20h6v2.56c0,0,1.93-2.56,5.81-2.56 c3.97,0,7.19,2.73,7.19,8.26V39z"></path>
</svg>
            </div>
            linkedin giulia mariano
          </a>
          <!-- curriculum -->
          <div>
            <a href="/src/assets/docs/Giulia Mariano.pdf" download="Giulia Mariano.pdf" class=" link-light fs-4">
              Scarica il mio CV
            </a>
          </div>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>
<script>
import { store } from "../store.js";
import axios from "axios";
import AppCardsAnimation from "../components/AppCardsAnimation.vue";
import AppHero from "../components/AppHero.vue";
import newCards from "../components/newCards.vue";
import Loader from "../components/Loader.vue";

export default {
  name: "AppHome",

  components: {
    AppCardsAnimation,
    AppHero,
    newCards,
    Loader,
  },
  data() {
    return {
      store,
      currentPage: 1,
      totalPages: 0,
      showFrontend: false,
      showBackend: false,
    };
  },
  watch: {
    '$route': 'scrollToHash' // Watch for route changes
  },
  methods: {
    getAllTechnologies() {
      axios
        .get(this.store.apiUrl + "technologies")
        .then((res) => {
          console.log("technologies");
          console.log(res.data);
          if (res.data.results) {
            this.store.technologies = res.data.results;
          } else {
            this.store.technologies = res.data;
          }
          console.log(this.store.technologies); // Verifica se i dati sono corretti
        })
        .catch((error) => {
          console.error("Errore durante il recupero delle tecnologie:", error);
        });
    },

    getAllPosts(page) {
      axios
        .get(this.store.apiUrl + "posts")
        .then((res) => {
          console.log("posts");
          console.log(res.data);
          if (res.data.results) {
            this.store.posts = res.data.results;
          } else {
            this.store.posts = res.data;
          }
          console.log(this.store.posts); // Verifica se i dati sono corretti
        })
        .catch((error) => {
          console.error("Errore durante il recupero dei posts:", error);
        });
    },

    filteredPosts() {
      console.log(`presaaaaaa`);
      console.log(this.store.filteredPosts);
      this.store.isLoading = true;
      this.store.filteredPosts = [];
      try {
        if (this.showFrontend === true && this.showBackend === false) {
          this.store.filteredPosts = this.store.posts.filter(
            (post) => post.category_id === 1
          );
        } else if (this.showBackend === true && this.showFrontend === false) {
          this.store.filteredPosts = this.store.posts.filter(
            (post) => post.category_id === 2
          );
        } else if (this.showFrontend === true && this.showBackend === true) {
          this.store.filteredPosts = this.store.posts.filter(
            (post) => post.category_id === 3
          );
        } else if (this.showFrontend === false && this.showBackend === false) {
          this.store.filteredPosts = this.store.posts;
          console.log(`ci passo`);
        } else {
          this.store.filteredPosts = this.store.posts;
        }
      } finally {
        this.store.isLoading = false;
        console.log(this.store.filteredPosts);
      }
    },
    scrollToHash() {
      // Check if there is a hash in the URL
      if (this.$route.hash) {
        const element = document.querySelector(this.$route.hash);
        if (element) {
          element.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      }
    }
  },
  created() {
    this.getAllTechnologies();
    this.getAllPosts();
    //this.filteredPosts();
  },
  mounted() {
    this.scrollToHash();
  },
};
</script>
<style lang="scss" scoped>
@use "../assets/style/partials/variables" as *;
@use "../assets/style//partials/borderfluid" as *;
.background {
  position: relative;
  width: 100%;
  height: 70vh;
  overflow: hidden;
}
.background2 {
  position: relative;
  width: 100%;
  height: 108vh;
  overflow-y: scroll;
  overflow-x: hidden;
}
.filter-video {
  filter: grayscale(20%) brightness(50%);
}

.background-fullstack {
  position: relative;
  width: 100%;
  height: 60vh;
  overflow: hidden;
}
/* Nascondi la barra di scorrimento */
::-webkit-scrollbar {
  display: block;
}

/* Imposta la larghezza della barra di scorrimento */
::-webkit-scrollbar {
  width: 10px;
}

/* Imposta il colore della barra di scorrimento e del track */
::-webkit-scrollbar {
  background-color: transparent; /* Colore del track */
}

::-webkit-scrollbar-thumb {
  background-color: $purple6; /* Colore della barra di scorrimento */
  border-radius: 5px; /* Bordo arrotondato */
}

#video-background1,
#background2,
#video-background3 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.color-1 {
  background: $purple1;
  background: linear-gradient(
    180deg,
    $purple2 27%,
    $purple3 57%,
    $purple4 100%
  );
  // height: 100vh;
}

.color-2 {
  background: $purple1;
  background: linear-gradient(
    180deg,
    $purple4 27%,
    $purple5 57%,
    $purple6 100%
  );
  height: 100vh;
}

.color-3 {
  background: $purple2;
  background: linear-gradient(
    180deg,
    $purple6 27%,
    $purple7 57%,
    $purple8 100%
  );
}
.color-4 {
  background: $purple8;
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
.icon {
  filter: invert(1);
  svg {
    height: 40px;
    padding-right: 20px;
  }
}

.content-overlay {
  background: rgba(0, 0, 0, 0.3); /* Aggiungi una sfumatura in overlay */
}
.invert-img {
  filter: invert(1);
}
.my-icon-container {
  display: flex;
  width: fit-content;
  height: 300px;
  justify-content: center; /* Centra le icone orizzontalmente */
  overflow: hidden;
}
.my-icon {
  margin-left: 100px;
  flex-wrap: nowrap;
  height: 100%;
  width: 100px;
  z-index: 2;
  filter: drop-shadow(3px 3px 10px $purple5);
  transition: transform 2s;
  animation: scroll 50s linear infinite;
}
.container-projects {
  height: 60vh;
  width: 100%;
  padding-top: 420px;
  overflow-y: scroll;
  .project {
    background-color: rgba(0, 0, 0, 0.3);
  }
  .project:hover {
    background-color: rgba(66, 66, 66, 0.3);
    cursor: pointer;
  }
}

@keyframes scroll {
  0% {
    transform: translate(0px);
  }
  50% {
    transform: translate(-1450%);
  }
  100% {
    transform: translate(0px);
  }
}

.my-icon:hover {
  transform: scale(1.4);
  cursor: pointer;

  .name-icon {
    opacity: 1;
    transition: 0.5s;
  }
}

.name-icon {
  opacity: 0;
  font-size: 2em;
  transition: 0.5s;
}

.div-1 {
  background-color: rgb(34, 15, 73);
  width: 30%;
  position: absolute;
  top: 30%;
  left: 10%;
  padding: 60px;
}

.div-2 {
  background-color: rgba(0, 0, 0, 0.5);
  width: 30%;
  position: absolute;
  bottom: 30%;
  right: 10%;
  padding: 60px;
  z-index: 2;
}
@media screen and (max-width: 1024px) {
  .div-1 {
    background-color: rgb(34, 15, 73);
    width: 80%;
    position: absolute;
    top: 60%;
    left: 10%;
    padding: 60px;
  }

  .div-2 {
    background-color: rgba(0, 0, 0, 0.5);
    width: 80%;
    position: absolute;
    bottom: 50%;
    right: 10%;
    padding: 60px;
    z-index: 2;
  }

  .background-fullstack {
    height: 120vh;
    overflow: hidden;
  }
}
/* Stile generale per le checkbox */
input[type="checkbox"] {
  display: none;
}

/* Stile del testo per le checkbox non selezionate */
input[type="checkbox"] + label {
  background-color: white;
  color: $purple8;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
}

input[type="checkbox"] + label:hover {
  background-color: rgb(172, 171, 171);
}

/* Stile del testo per le checkbox selezionate */
input[type="checkbox"]:checked + label {
  background-color: $purple1;
  color: black;
  box-shadow: 0px 0px 10px $purple1;
}

/* Aggiungi spazio tra il testo e il bordo della checkbox */
input[type="checkbox"] + label::before {
  content: "";
  display: inline-block;
  width: 1px;
  height: 1px;
}
.text-git {
  transition: all 1s;
}
.text-git:hover {
  transform: scale(1.1);
  text-decoration: underline !important;
}
</style>
