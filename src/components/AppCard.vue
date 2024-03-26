<template>
     
        <router-link :to="{ name: 'single-post', params: { slug: post.slug || ''} }">
          <div class="card d-flex justify-content-between border-0 p-1 bg-transparent position-relative h-auto">
      <img :src="`${store.imgPath}images/${post.title}.png`" :alt="post.title" class="card-top"> 
      <!-- <p class="card-text text-light ">{{ post.body.substring(0, 80) + '...' }}</p> -->
      <div class="position-absolute d-flex justify-content-center align-items-center align-content-center myoverlay">
       <h5  class="btn text-light  my-1">{{ post.title }}</h5> 
      </div>
      </div>
    </router-link>
  </template>
  
  <script>
  import {store} from '../store.js';
    export default {
      name: "AppCard",
      props: ['post'],
      data(){
        return {
          store
        }
      },
      mounted() {
        console.log('Slug:', this.post.slug);
      },
    }
  </script>
  
  <style lang="scss" scoped>
  @use '../assets/style/partials/variables' as *;
  .card{
    height: 80%;
    img{
      object-fit: cover;
      object-position: 50% 0%;
    }
  }
  .card-top{
    width: 100%;
    height: 200px;
  }
  .myoverlay{
    background-color: rgba(0, 0, 0, 0.3);
    width: 100%;
    height: 100%;
    .btn{
      background-color:  rgb(70, 27, 156);
    }
  }
  .myoverlay:hover{
    background-color: rgba(0, 0, 0, 0);
    width: 100%;
    height: 100%;
    .btn{
      background-color:white;
      color: rgb(70, 27, 156)!important ;
      border: 1px solid rgb(70, 27, 156);
      font-weight: 600;
    }
  }
  </style>