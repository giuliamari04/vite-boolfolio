<template>
  <main class="container">
    <h1 class="text-primary my-3">Post List</h1>
    <div class="row">
      <div class="col-12 col-md-4 col-lg-3" v-for="post in store.posts" :key="post.id">
        <AppCard :post="post"></AppCard>
      </div>
    </div>
    <nav aria-label="..." class="d-flex justify-content-center align-content-center my-4">
      <ul class="pagination">
        <li class="page-item" :class="{'disabled': store.pagination.current_page === 1}">
          <button class="page-link" :disabled="store.pagination.current_page === 1" @click="getAllPosts(store.pagination.current_page - 1)">Previous</button>
        </li>
        <li class="page-item" v-for="n in store.pagination.last_page" :key="n">
          <button class="page-link" @click="getAllPosts(n)">{{ n }}</button>
        </li>
        <li class="page-item" :class="{'disabled': store.pagination.current_page === store.pagination.last_page}">
          <button class="page-link" :disabled="store.pagination.current_page === store.pagination.last_page" @click="getAllPosts(store.pagination.current_page + 1)">Next</button>
        </li>
      </ul>
    </nav>
  </main>
</template>

<script>
import { store } from "../store.js";
import axios from "axios";
import AppCard from "../components/AppCard.vue";

export default {
  name: "AppPosts",
  components: {
    AppCard,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getAllPosts(page) {
      axios.get(this.store.apiUrl + "posts?page=" + page).then((res) => {
        console.log(res.data);
        this.store.posts = res.data.results.data;
        this.store.pagination = res.data.results; // Assume che il backend restituisca i dati della paginazione
      });
    },
  },
  created() {
    this.getAllPosts(1); // Carica la prima pagina all'avvio
  },
};
</script>

<style lang="scss" scoped>
  /* Stili CSS specifici per il componente */
</style>
