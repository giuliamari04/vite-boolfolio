<template>
    <div class="container">
      <h1 class="text-primary my-3">{{ post.title }}</h1>
      <div class="mb-3">
        <!-- <div v-if="count(post.category)>0">
          <span class="badge bg-primary text-decoration-none me-1 ">{{ post.category.name}}</span>
        </div>
        <div v-if="count(post.technology)>0">
            <span class="badge bg-secondary text-decoration-none">{{ post.technologies[0].name}}</span>
        </div> -->
      
      </div>
    <img :src="`${store.imgPath}${post.image}`" :alt="post.title"> 
    <div>
      {{ post.body }}
    </div>
    
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  import {store} from '../store.js';
    export default {
      name: "SinglePost",
      data(){
        return {
          store,
          post: null,
          technologies: null
        }
      },
      methods: {
        getPostData(){
          axios.get (this.store.apiUrl + 'posts/' + this.$route.params.slug).then((res) => {
            console.log(res.data);
            this.post = res.data.results;
          }).catch((err) => {
            console.log(err);
          })
        }
      },
      created(){
        console.log('Created Slug:', this.$route.params.slug);
        this.getPostData()
      },
      mounted() {
  console.log('Mounted Slug:', this.$route.params.slug);
},

    }
  </script>
  
  <style lang="scss" scoped>
  img{
    max-width: 300px;
  }
  
  </style>