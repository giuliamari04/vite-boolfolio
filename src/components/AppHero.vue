 <template>
  
 <!-- hero -->
 <div class="video-background ">
    <video autoplay muted loop id="video-background1" class="filter-video">
      <source
        src="/src/assets/images/Isometric Apps Development Background video _ Footage _ Screensaver.mp4"
        type="video/mp4"
      />
      Il tuo browser non supporta il tag video.
    </video>
    <div class="content content-overlay">
      <div class="d-flex justify-content-center align-items-center align-content-center h-100">
        <div class="container h-100">
          <div class="row d-flex h-100">
            <div
              class="col-8 d-flex justify-content-center flex-column text-light my-sm-container"
            >
              <h2 class="display-5 fw-semibold">Giulia Mariano</h2>
              <h1 class="display-1">MyPortfolio</h1>
              <h3 class="display-5">Web Developer</h3>
            </div>
            <div class="col d-flex justify-content-end  align-items-center my-sm-container">
              <div class="profile-picture overflow-hidden">
                <img
                  src="/src/assets/images/Mee.png"
                  alt="my-image"
                  class="w-100"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "AppHero",

  data() {
    return {
      
    };
  },
  methods: {
  }
}
</script>
<style lang="scss" scoped>
.video-background {
  position: relative;
  width: 100%;
  height: 60vh;
  overflow: hidden;
}

.filter-video {
  filter: grayscale(20%) brightness(50%);
}

#video-background1 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.content {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  color: white;

  .col-8 {
    text-align: end;
    h1,
    h2,
    h3 {
      text-shadow: 0px 0px 20px black;
    }
  }
}
.icon{
 filter: invert(1);
  svg{
    height: 40px;
    padding-right: 20px;
  }
}
.profile-picture {
  width: 400px;
  height: 400px;
  border-radius: 50%;
  border: 8px solid rgba(64, 43, 142, 0.59);
  -webkit-box-shadow: 0px 0px 186px 27px rgba(64, 43, 142, 0.59);
  -moz-box-shadow: 0px 0px 186px 27px rgba(64, 43, 142, 0.59);
  box-shadow: 0px 0px 186px 27px rgba(64, 43, 142, 0.59);
}
.content-overlay {
  background: rgba(0, 0, 0, 0.3); /* Aggiungi una sfumatura in overlay */
}

@media screen and (max-width: 1025px) {
  .my-sm-container{
    margin: auto;
    margin: 0;
    display: flex;
    justify-content: center !important;
    width: 100%;
    text-align: center !important;
  }
  .profile-picture {
  width: 250px;
  height: 250px;
  padding-bottom: 80px;
}
}
</style>