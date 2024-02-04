<template>
    <div class="card">
      <img :src="`${store.imgPath}${post.image}`" :alt="post.title" class="card-top"> 
      <p class="card-text">{{ post.body.substring(0, 80) + '...' }}</p>
      <router-link :to="{ name: 'single-post', params: { slug: post.slug || ''} }" class="btn btn-primary my-1">
        {{ post.title }}</router-link>
  
    </div>
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
  
  .card-top{
    width: 100%;
    height: 200px;
  }
  
  </style>