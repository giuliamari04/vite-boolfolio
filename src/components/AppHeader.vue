<template>
    <nav class="navbar navbar-expand-lg color-1">
    <div class="container">
      <a class="navbar-brand text-light" href="#">Boolfolio</a>
      <button class="navbar-toggler bg-white" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          
          <li class="nav-item text-light" v-for="item in menu" :key="item.name">
            <router-link class="nav-link text-light" active-class="active" :to="{name: item.name}">{{ item.label }}</router-link> 
          </li>
          
        </ul>
       
      </div>
    </div>
  </nav>
  </template>
  
  <script>
    export default {
      name: "AppHeader",
      data(){
        return {
          menu: [
            {
              label: 'Home', 
              name: 'home', 
            },
            {
              label: 'Pojects', 
              name: 'posts', 
            },
            {
            label: 'Contacts', 
            name: 'contacts',         
          },

  
          ]
        }
      }
    }
  </script>
  
  <style lang="scss" scoped>
  nav{
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 3;
    min-height: 8vh;
    padding: 10px 20px;
  }
  .nav-link{
    text-transform: uppercase;
  }
  .nav-link:hover{
    color: #0d6efd;
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