<template>
  <div class="home">
    <div :class="'container header ' + headerFade">
      <section class="title-section">
        <h1 class="title-text fadeleft-text">Mihail Timoshenko</h1>
        <h2 class="title-text faderight-text">Frontend Developer</h2>
      </section>

      <div class="decoration-top">
        <div class="circle-decor-2"></div>
        <div class="circle-decor-3"></div>
        <div class="circle-decor-1"></div>
      </div>

      <div class="decoration-bottom">
        <div class="circle-decor-bottom-1"></div>
      </div>

    </div>


    <div :class="'container about ' + aboutFade">
      <About></About>
    </div>

    <div :class="'container skills ' + skillsFade">
      <h2>Skills</h2>
    </div>

    <div :class="'container portfolio ' + portfolioFade">
      <h2>Portfolio</h2>
    </div>

    <div :class="'container contacts ' + contactsFade">
      <h2>Contacts</h2>
    </div>

    <div class="nav">
      <div class="btn-container left-btn">
        <button class="nextButton" v-if="slide !== 0" @click="slide -= 1">
          <i v-if="slide == 1 || slide == 3" style="color:#330a50" class="fas fa-chevron-left"></i>
          <i v-else class="fas fa-chevron-left"></i>
        </button>
      </div>
      <div class="btn-container right-btn">
        <button class="nextButton" v-if="slide !== 4" @click="slide += 1">
          <i v-if="slide == 1 || slide == 3" style="color:#330a50" class="fas fa-chevron-right"></i>
          <i v-else class="fas fa-chevron-right"></i>
        </button>
      </div>
    </div>
    

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import About from "@/components/About.vue"

export default {
  name: 'Home',
  components:{
    About
  },
  data(){
    return{
      slide: 0,
      test: "header",
      headerFade: "",
      aboutFade: "",
      skillsFade: "",
      portfolioFade: "",
      contactsFade: ""
      
    }
  },
  mounted(){

  },
  watch:{
    slide: function(){
      if(this.slide < 0 || this.slide > 4){
        this.slide = 0
      }
      switch (this.slide) {
        case 0:
          this.headerFade = "fadeIn"
          this.aboutFade = "fadeOut"
          this.skillsFade = "fadeOut"
          this.portfolioFade = "fadeOut"
          this.contactsFade = "fadeOut"


          break;
        case 1:
          this.headerFade = "fadeOut"
          this.aboutFade = "fadeIn"
          this.skillsFade = "fadeOut"
          this.portfolioFade = "fadeOut"
          this.contactsFade = "fadeOut"
          break;
        case 2:
          this.headerFade = "fadeOut"
          this.aboutFade = "fadeOut"
          this.skillsFade = "fadeIn"
          this.portfolioFade = "fadeOut"
          this.contactsFade = "fadeOut"
          break;
        case 3:
          this.headerFade = "fadeOut"
          this.aboutFade = "fadeOut"
          this.skillsFade = "fadeOut"
          this.portfolioFade = "fadeIn"
          this.contactsFade = "fadeOut"
          break;
        case 4:
          this.headerFade = "fadeOut"
          this.aboutFade = "fadeOut"
          this.skillsFade = "fadeOut"
          this.portfolioFade = "fadeOut"
          this.contactsFade = "fadeIn"
          break;
      
        default:
          break;
      }
    }
  }

}
</script>

<style lang="scss">

.header{
  height: 100vh;
  width: 100vw;
  background-color: #330a50;
  color: #f6fdff;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  z-index: 5;
  position: fixed;
  top: 0;
  left: 0;

}

.title-section{
  h1{
    font-size: 62px;
  }
  h2{
    font-size: 42px;
  }
  .title-text{
    opacity: 0;
    animation: fade-text 3s forwards;
  }

}

// .nav{
//   height: 100vh;
//   width: 100vw;
//   display: flex;
//   justify-content: space-between;
//   align-items: center;
//   position: fixed;
//   bottom: 0;
//   left: 0;
//   // z-index: 99;
// }

.fadeOut{
  animation: fadeOut 1s forwards;
}

.fadeIn{
  animation: fadeIn 1s forwards;  
}


.about{
  height: 100vh;
  width: 100vw;
  background-color: white;
  color: #263747;
  justify-content: center;
  align-items: center;
  font-size: 32px;
  z-index: 1;
  position: fixed;
  top: 0;
  left: 0;
}

.skills{
  height: 100vh;
  width: 100vw;
  background-color: #330a50;
  color: white;
  justify-content: center;
  align-items: center;
  font-size: 32px;
  z-index: 2;
  position: fixed;
  top: 0;
  left: 0;
}

.portfolio{
  height: 100vh;
  width: 100vw;
  background-color: white;
  color: #263747;
  justify-content: center;
  align-items: center;
  font-size: 32px;
  z-index: 3;
  position: fixed;
  top: 0;
  left: 0;
}

.contacts{
  height: 100vh;
  width: 100vw;
  background-color: #330a50;
  color: white;
  justify-content: center;
  align-items: center;
  font-size: 32px;
  z-index: 4;
  position: fixed;
  top: 0;
  left: 0;
}
// Decorations
.circle-decor-1{
  width: 200px;
  height: 200px;
  border-radius: 50%;
  opacity: 0.8;
  background-color: rgb(196, 69, 168);
  animation: decorAnim-1 7s infinite;
  position: absolute;
  right: -68px;
  top: -5px;
}

.circle-decor-2{
  width: 300px;
  height: 300px;
  border-radius: 50%;
  animation: decorAnim-2 7s infinite;
  background-color: rgb(238, 84, 205);
  opacity: 0.9;
  position: absolute;
  right: -6px;
  top: -118px;
}

.circle-decor-3{
  width: 250px;
  height: 250px;
  border-radius: 50%;
  animation: decorAnim-3 7s infinite;
  background-color: rgb(240, 114, 213);
  opacity: 0.8;
  position: absolute;
  right: -30px;
  top: -44px;
}


.circle-decor-bottom-1{
  width: 450px;
  height: 450px;
  border-radius: 50%;
  animation: decorAnim-3 7s infinite;
  background-color: rgb(240, 114, 213);
  opacity: 0.8;
  position: absolute;
  left: -195px;
  bottom: 0px;
}

// Decorations end


.container{
  display: flex;
}

.nextButton{
  border: none;
  background-color: transparent;
  font-size: 52px;
  color: white;
  padding: 10px;
  cursor: pointer;
  animation: navButton 2s infinite;
}

.right-btn{
  position: fixed;
  top: 50%;
  right: 0;
  z-index: 99;
}

.left-btn{
  position: fixed;
  top: 50%;
  left: 0;
  z-index: 99;
}


@keyframes fadeOut {
  0%{
    opacity: 1;
    top: 0;
  }
  100%{
    // opacity: 0;
    top: -101%;
  }
}

@keyframes fadeIn {
  0%{
    opacity: 0;
    top: -101%;
  }
  100%{
    opacity: 1;
    top: 0;
  }
}

@keyframes navButton {
  0%{
    transform: scale(0.7, 0.7);
    opacity: 0.5;
  }
  50%{
    transform: scale(1.2, 1.2);
    opacity: 1;
  }
  100%{
    transform: scale(0.7, 0.7);
    opacity: 0.5;
  }
}

@keyframes fade-text {
  0%{
    opacity: 0;
  }
  100%{
    opacity: 1;
  }
}

// decor animate
@keyframes decorAnim-1 {
  0%{
    opacity: 1;
    background-color: rgb(196, 69, 168);
  }
  40%{
    opacity: 0.6;
    background-color: rgb(240, 114, 213);
  }
  75%{
    opacity: 0.8;
    background-color: rgb(238, 84, 205);

  }
  100%{
    opacity: 1;
    background-color: rgb(196, 69, 168);
  }
}

@keyframes decorAnim-2 {
  0%{
    opacity: 0.5;
    background-color: rgb(238, 84, 205);
  }
  40%{
    opacity: 0.9;
    background-color: rgb(196, 69, 168);
  }
  75%{
    opacity: 0.6;

    background-color: rgb(240, 114, 213);

  }
  100%{
    opacity: 0.5;
    background-color: rgb(238, 84, 205);
  }
}

@keyframes decorAnim-3 {
  0%{
    opacity: 0.5;
    background-color: rgb(240, 114, 213);
  }
  40%{
    opacity: 0.9;
    background-color: rgb(238, 84, 205);
  }
  75%{
    opacity: 0.6;
    background-color: rgb(196, 69, 168);


  }
  100%{
    opacity: 0.5;
    background-color: rgb(240, 114, 213);

  }
}


// decor animate end
</style>
