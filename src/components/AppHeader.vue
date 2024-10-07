<template>
    <nav class="navbar navbar-expand-lg color-1">
    <div class="container">
      <router-link class="navbar-brand text-light" :to="{ name: 'home', hash: '#home'}" href="#">Boolfolio</router-link>
      <button class="navbar-toggler bg-toggle" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="my-toggler-icon">
          <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="40" height="40" viewBox="0 0 64 64">
          <linearGradient id="BTq72ScaTZ1UBmT8omo2pa_44024_gr1" x1="32" x2="32" y1="5.333" y2="59.867" gradientUnits="userSpaceOnUse" spreadMethod="reflect"><stop offset="0" stop-color="#1a6dff"></stop><stop offset="1" stop-color="#c822ff"></stop></linearGradient><path fill="url(#BTq72ScaTZ1UBmT8omo2pa_44024_gr1)" d="M32,58C17.663,58,6,46.337,6,32S17.663,6,32,6s26,11.663,26,26S46.337,58,32,58z M32,8 C18.767,8,8,18.767,8,32s10.767,24,24,24s24-10.767,24-24S45.233,8,32,8z"></path><linearGradient id="BTq72ScaTZ1UBmT8omo2pb_44024_gr2" x1="32" x2="32" y1="5.333" y2="59.867" gradientUnits="userSpaceOnUse" spreadMethod="reflect"><stop offset="0" stop-color="#1a6dff"></stop><stop offset="1" stop-color="#c822ff"></stop></linearGradient><path fill="url(#BTq72ScaTZ1UBmT8omo2pb_44024_gr2)" d="M32,52c-11.028,0-20-8.972-20-20s8.972-20,20-20s20,8.972,20,20S43.028,52,32,52z M32,14 c-9.925,0-18,8.075-18,18s8.075,18,18,18s18-8.075,18-18S41.925,14,32,14z"></path><linearGradient id="BTq72ScaTZ1UBmT8omo2pc_44024_gr3" x1="32" x2="32" y1="21.5" y2="26.336" gradientUnits="userSpaceOnUse" spreadMethod="reflect"><stop offset="0" stop-color="#6dc7ff"></stop><stop offset="1" stop-color="#e6abff"></stop></linearGradient><path fill="url(#BTq72ScaTZ1UBmT8omo2pc_44024_gr3)" d="M42,25c0,0.552-0.448,1-1,1H23c-0.552,0-1-0.448-1-1v-2c0-0.552,0.448-1,1-1h18 c0.552,0,1,0.448,1,1V25z"></path><linearGradient id="BTq72ScaTZ1UBmT8omo2pd_44024_gr4" x1="32" x2="32" y1="29.333" y2="34.5" gradientUnits="userSpaceOnUse" spreadMethod="reflect"><stop offset="0" stop-color="#6dc7ff"></stop><stop offset="1" stop-color="#e6abff"></stop></linearGradient><path fill="url(#BTq72ScaTZ1UBmT8omo2pd_44024_gr4)" d="M42,33c0,0.552-0.448,1-1,1H23c-0.552,0-1-0.448-1-1v-2c0-0.552,0.448-1,1-1h18 c0.552,0,1,0.448,1,1V33z"></path><linearGradient id="BTq72ScaTZ1UBmT8omo2pe_44024_gr5" x1="32" x2="32" y1="37" y2="41.337" gradientUnits="userSpaceOnUse" spreadMethod="reflect"><stop offset="0" stop-color="#6dc7ff"></stop><stop offset="1" stop-color="#e6abff"></stop></linearGradient><path fill="url(#BTq72ScaTZ1UBmT8omo2pe_44024_gr5)" d="M42,41c0,0.552-0.448,1-1,1H23c-0.552,0-1-0.448-1-1v-2c0-0.552,0.448-1,1-1h18 c0.552,0,1,0.448,1,1V41z"></path>
          </svg>
        </span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item text-light">
            <router-link  @click="closeMenu"
            :to="{ name: 'home', hash: '#home'}" href="#" class="nav-link text-light">home</router-link>
          </li>

          <li class="nav-item text-light">
            <router-link  @click="closeMenu" :to="{ name: 'home', hash: '#technologies' }" href="#" class="nav-link text-light">technologies</router-link>
          </li>

          <li class="nav-item text-light">
            <router-link  @click="closeMenu" :to="{ name: 'home', hash: '#projects' }" href="#" class="nav-link text-light">projects</router-link>
          </li>

          <li class="nav-item text-light">
            <router-link  @click="closeMenu" :to="{ name: 'home', hash: '#contacts' }" href="#" class="nav-link text-light">contacts</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
  </template>
  
  <script>
    export default {
      name: "AppHeader",
      props: {
        scrollToSection: {
          type: Function,
          required: true
        },
      },
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
      },
      methods:{
        closeMenu() {
      // Trova il pulsante del navbar-toggler
      const navbarToggler = document.querySelector('.navbar-toggler');

      // Verifica se la navbar è aperta
      const navbarCollapse = document.querySelector('#navbarSupportedContent');
      if (navbarCollapse.classList.contains('show')) {
        // Se la navbar è aperta, simula il click per chiuderla
        navbarToggler.click();
      }
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