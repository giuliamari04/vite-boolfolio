<template>
  <div class="color-1 mt-5">
    <div v-if="post">
      <div class="container">
        <h1 class="text-light display-5 text-center py-3 py-3">
          {{ post.name }}
        </h1>
        <div class="mb-3">
          <!-- <div v-if="count(post.category)>0">
          <span class="badge bg-primary text-decoration-none me-1 ">{{ post.category.name}}</span>
        </div>-->
          <!-- <div v-if="count(post.technology)>0"> -->
        </div>

        <!-- </div> -->
        <div class="row py-4 w-100 d-lg-flex">

          <!-- prima colonna -->
          <div class=" col-lg-6 col-md-8 m-auto img-show px-5">
            <section id="page" class="video-container">
              <div class="w-100 d-flex justify-content-between align-content-center flex-wrap">
                 <h3 class="pb-4 text-light">Preview</h3>
                 <span class="text-light pb-4 pt-2 link-repo">
                   <a :href=" post.link_repo " target="_blank" class=" text-light">Link repo {{ post.name }}</a>
                 </span>
              </div>
             
              <div class="pb-5 video-wrapper">
                <video
                  autoplay
                  muted
                  loop
                  :src="'/src/assets/images/' + post.name + '.mp4'"
                  class="video"
                ></video>
              </div>
            </section>
          </div>
          <!-- colonna descrizioni testuali -->
          <div class=" col-lg col-md-8 m-auto px-5 ">
            <h3 class="text-light pt-5">Description</h3>
            <div class="description overflow-scroll mt-3">
               <div>
              <p class="text-light">
              {{ post.description }} 
              </p>
            </div>
            </div>
           
            <h3 class="text-light py-2">Technologies</h3>
            <!-- div technologies -->
            <div class="d-flex flex-wrap">
              <span
                v-for="technology in post.technologies"
                class="badge bg-secondary mx-1 p-2 my-1"
              >
                {{ technology.name }}
              </span>
            </div>
          </div>

        </div>
      </div>
    </div>
    <div v-else>
      <p>Caricamento in corso...</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../store.js";
export default {
  name: "SinglePost",
  data() {
    return {
      store,
      post: null,
      technologies: null,
    };
  },
  methods: {
    getPostData() {
      const slug = this.$route.params.slug;
      console.log("Requesting post with slug:", slug); // Aggiungi questo per il debug
      store.isLoading = true;
      axios
        .get(store.apiUrl + "posts/" + slug + "/")
        .then((res) => {
          console.log(res.data);
          this.post = res.data;
        })
        .catch((err) => {
          console.log(err.response.status); // Per verificare lo stato dell'errore
          if (err.response.status === 404) {
            console.error("Post non trovato");
          }
        })
        .finally(() => {
          store.isLoading = false; // Al termine della richiesta, imposta isLoading su false
        });
    },

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
  },
  created() {
    console.log("Created Slug:", this.$route.params.slug);
    this.getPostData();
    this.getAllTechnologies();
  },
  mounted() {
    console.log("Mounted Slug:", this.$route.params.slug);
  },
};
</script>

<style lang="scss" scoped>
.container {
  min-height: 83vh;
  img {
    width: 100%;
    top: 0;
    border-radius: 20px;
    box-shadow: 5px 5px 20px rgb(215, 154, 255);
  }
}
.row {
  min-height: 69.4vh;
  .img-show {
    max-height: 50vh;
    // overflow: hidden;
    max-width: 1200px;
    padding: 0px;
  }
}
.video-container {
  display: flex;
  flex-direction: column; /* Per disporre gli elementi in colonna */
  align-items: center; /* Centra gli elementi orizzontalmente */
  justify-content: center; /* Centra gli elementi verticalmente */
}

.video-wrapper {
  width: 100%; /* Occupare tutta la larghezza della colonna */
  max-height: 400px; /* Limita l'altezza massima del video */
  overflow: hidden; /* Nascondi eventuali parti del video che escono */
}

.video {
  width: 100%; /* Rende il video responsivo */
  height: auto; /* Mantiene le proporzioni del video */
  object-fit: cover; /* Adatta il video al contenitore senza distorsioni */
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
#page {
  height: fit-content;
  width: 100%;
  div {
    display: flex;
    justify-content: center;
    width: 100%;
    img {
      width: 90%;
    }
  }
}
.description{
  height: 35vh;
  padding: 20px 10px;
  background-color: rgba(255, 255, 255, 0.185);
  border-radius: 10px;
}
.link-repo{
  a{
    text-decoration: none;
  }

}
.link-repo:hover{
  text-decoration: underline;
  
}
@media screen and (max-width: 767px) {
  
}
</style>
