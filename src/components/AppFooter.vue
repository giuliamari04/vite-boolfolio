<template>
    <footer class="text-center d-flex justify-content-center align-items-center py-3 ">
    <p>&copy; Boolfolio 2024. <br>Made by Giulia Mariano. <br> <span class="testo-mini">Autorizzo il trattamento dei dati personali nel mio cv-portfolio in base all'art. 13 GDPR 679/16</span></p>
    
    </footer>
  </template>
  
  <script>
    export default {
      name: "AppFooter",
      data(){
        return {
          
        }
      }
    }
  </script>
  
  <style lang="scss" scoped>
  footer{
    margin: 0;
    color: white;

    background: rgb(34, 15, 73);
    background: linear-gradient(
      200deg,
      rgba(34, 15, 73, 1) 27%,
      rgba(15, 7, 39, 1) 57%,
      rgba(2, 1, 12, 1) 100%
    );

    .testo-mini{
      font-size: 0.8em;
    }
  }
  
  </style>