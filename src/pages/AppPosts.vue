<template>
  <main class=" color-1 pt-5">
    <div class="container d-flex flex-column justify-content-center align-items-center">
       <h1 class="text-light display-5 py-3 ">Post List</h1>
    <div class="row h-auto  d-flex  justify-content-center">
      <div class="col-12 col-md-4 " v-for="post in store.posts" :key="post.id">
        <AppCard :post="post"></AppCard>
      </div>
    </div>
    <nav aria-label="..." class="d-flex justify-content-center py-5">
      <ul class="pagination">
        <li class="page-item " :class="{'disabled': store.pagination.current_page === 1}">
          <button class="page-link" :disabled="store.pagination.current_page === 1" @click="getAllPosts(store.pagination.current_page - 1)">Previous</button>
        </li>
        <li class="page-item" v-for="n in store.pagination.last_page" :key="n">
          <button class="page-link bg-transparent text-light px-3" @click="getAllPosts(n)">{{ n }}</button>
        </li>
        <li class="page-item" :class="{'disabled': store.pagination.current_page === store.pagination.last_page}">
          <button class="page-link" :disabled="store.pagination.current_page === store.pagination.last_page" @click="getAllPosts(store.pagination.current_page + 1)">Next</button>
        </li>
      </ul>
    </nav>
    </div>
   
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
  .container{
    min-height: 100vh;
  }
  .row{
    height: 50vh;
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
</style>
