<template>
  <div class="color-1 mt-5">
    <div class="container">
      <h1 class="text-light display-5 py-3 py-3">{{ post.title }}</h1>
      <div class="mb-3">
        <!-- <div v-if="count(post.category)>0">
          <span class="badge bg-primary text-decoration-none me-1 ">{{ post.category.name}}</span>
        </div>-->
        <!-- <div v-if="count(post.technology)>0"> -->
        
        </div> 
    
      <!-- </div> -->
      <div class="row py-4">
        <div class="col img-show">
           <img :src="`${store.imgPath}images/${post.title}.png`" :alt="post.title"> 
        </div> 
        <div class="col">
          <h3 class="text-light">Descriprion</h3>
          <p class="text-light">
             {{ post.body }}
          </p>
          <h3 class="text-light py-2">Technologies</h3>
          <div>
            <span  v-for="technology in post.technologies" class="badge bg-secondary mx-1 p-2">
              {{ technology.name}}
            </span>
          </div>
     
    </div>
      </div>
   
    
    </div>
    <section id="page">
      <h3 class="w-100 text-center pb-4 text-light fs-1 ">Preview</h3>
      <!-- <div v-if="'/src/assets/images/' + post.title + '.png'" class="pb-5">
        <img :src="'/src/assets/images/' + post.title + '.png'" :alt="post.title">
      </div> -->
      <div class="pb-5">
        <video autoplay muted loop :src="'/src/assets/images/'+ post.title + '.mp4'"></video>
      </div>
      
    </section>
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
  .container{
    height: 83vh;
    img{
    width: 100%;
    top: 0;
    border-radius: 20px;
    box-shadow: 5px 5px 20px rgb(215, 154, 255);
  }
  }
  .row{
    height: 69.4vh;
    .img-show{
      max-height: 55vh;
      overflow: hidden;max-width: 500px;
      padding: 30px;
     
    }
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
#page{
  height:fit-content;
  width: 100%;
  div{
    display: flex;
  justify-content: center;
  width: 100%;
  img{
    width: 90%;
  }
  }
}
  </style>