<template>
  <div class="home">
       <div id="nav">
        <div class="nav-wrapper">
          <div class="link-section">
              <router-link to="/about">About</router-link>
              <router-link to="/videos" @mouseover.native="showVc">Vidoes</router-link>
              <router-link to="/photos" @mouseover.native="showPc">Photos</router-link>
          </div>
          <div class="link-showcase">
            <div class="video-link-case" v-bind:class="{videocase: videoCase}">
               <video src="../assets/videos/dallas.mp4" loop="true" ref="dallas"></video>
            </div>
            <div class="photo-link-case" v-bind:class="{photocase: photoCase}">
              <img src="../assets/photos/01.jpg">
            </div>
          </div>
        </div>
       <div class="bottom-nav__section">
         <div class="bottom-nav__blocks">
          <a href="https://www.instagram.com/panabrad" target="_blank">Ig</a>
          <a href="https://www.linkedin.com/in/bradleykanter" target="_blank">In</a>
         </div>
          <div class="bottom-nav__blocks">
          <a href="https://anthonylan.com" target="_blank">Design — AL</a>
         </div>
          <div class="bottom-nav__blocks">
          <a href="#">Copyrights</a>
         </div>
       </div>
    </div>
       <div class="humburg-menu" @click="openNav">
          <span v-bind:class="{spantop: spanTActive}"></span>
          <span v-bind:class="{spanbottom: spanBActive}"></span>
        </div>
    <header class="v-header container" @click="handleScroll">
      <div class="top-header-section">
        <router-link to="/" class="brand-logo">
          <h1 class="top-name">Bradley</h1>
          <h1 class="bottom-name">Kanter</h1>
        </router-link>
      </div>
      <div class="fullscreen-video-wrap">
        <video src="../assets/videos/reel2015.mp4" autoplay loop="true" muted ref="video"></video>
      </div>
      <div class="contents">
        <div class="contents-wrap">
          <h1 class="header-top">Creator <span>&</span> </h1>
          <h1 class="cursive">Dreamer</h1>

          <div class="scroll-down">
            <span>touch to discover</span>
            <img src="../assets/down.svg">
          </div>
        </div>
      </div>
    </header>

    <div class="alpha-slider"></div>
    <div class="pro-alpha-slide">
      <div class="pro-al__wrapper">
        <h1>bk</h1>
        <div class="cover-slide"></div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

import { TweenMax } from 'gsap'
import { Expo } from 'gsap'



export default {
  name: 'home',
  data(){
    return{
      spanTActive: false,
      spanBActive: false,
      videoCase: false,
      photoCase: true
        
    }
  },
  components: {
    //HelloWorld
  },
  methods:{
    showPc(){
      this.videoCase = true
      this.photoCase = false
       const { dallas } = this.$refs
      dallas.play()
    },
     showVc(){
      this.videoCase = false
      this.photoCase = true
      const { dallas } = this.$refs
      dallas.play()
    },
  hideHeaders(){
    TweenMax.to('.header-top', .8, {display: 'none', autoAlpha: 0, ease: Expo.easeOut})
    TweenMax.to('.cursive', .8, {display: 'none', autoAlpha: 0, ease: Expo.easeOut})
  },
  
   openNav(){
      if(this.spanTActive == false){
       
         setTimeout(() => { 
          TweenMax.to('#nav', .5, {x: 0, ease: Expo.easeIn})
           this.spanTActive = true 
           this.spanBActive = true 
        }, 600)
      } else {
          
         
          setTimeout(() => { 
            TweenMax.to('#nav', .5, {x: '100%', ease: Expo.easeIn})
            this.spanTActive = false 
            this.spanBActive = false
        }, 600)
      }

      this.sliderUp()
    },
    sliderUp(){
      TweenMax.to('.alpha-slider', .5, {y: 0, ease: Expo.easeInOut})
      setTimeout(() => {
          TweenMax.to('.alpha-slider', .5, {y: '-100%', ease: Expo.easeInOut})
      }, 1000)
    },
    handleScroll(){

     setTimeout(() => {
       this.$router.push('/videos')
     }, 500)
        
    }
 
  },
    mounted(){
        
     const { video } = this.$refs;
     video.addEventListener('loadedmetadata', function() {
        //this.currentTime = 18
         TweenMax.to('.cover-slide', 10, {y: '-100%'})
         setTimeout(() => {
           TweenMax.to('.pro-alpha-slide', .3, {display: 'none', autoAlpha: 0})
            TweenMax.from('.header-top', .8, {x: 50, autoAlpha: 0, ease: Expo.easeOut, delay: 1})
           TweenMax.from('.cursive', .8, {x: -50, autoAlpha: 0, ease: Expo.easeOut, delay: 1})
         }, 5000)
      
      });
      setInterval(() => {
        video.currentTime = 18
      }, 100000)
  




  

  },

 
}
</script>


<style lang="scss" scoped>

@import '../assets/styles/_mixin.scss';

  .spantop{
     transform: rotate(45deg) translate(.5rem, 1rem);
  }
  .spanbottom{
    transform: rotate(-45deg) translate(-.5rem, 0rem);
  }



.videocase{
  display: none;
}

.photocase{
  display: none;
}




header{
  overflow-x: hidden;
  .contents{
    position: absolute;
    top: 0;
    left: 0;    
    display: table;
    height: 100%;
    width: 100%;
    z-index: 10;
    .contents-wrap{
      display: table-cell;
      height: 100%;
      width: 100%;
      vertical-align: middle;
      text-align: center;

      h1{
        font-size: 6rem;
         @include headerReset();
        span{
          display: inline-block;
          font-family: $headers;
          transform: rotate(90deg);
          font-size: 7rem;
          margin-left: -2rem;
        }
      }
      .header-top{
        margin-bottom: -3rem;
        font-size: 8.8rem;
        position: relative;
      }
      .cursive{
       @include curs();
       font-size: 10rem;
     
      }
      @media (max-width:550px) {
        overflow-x: hidden;
        h1{
          font-size: 3rem;
          span{
            font-size: 3rem;
            margin-left: -1rem;
          }
        }
        .header-top{
          font-size: 4rem;
           margin-bottom: 3rem;
        }
        .cursive{
          font-size: 5rem;
        }
      }
    }
  }
  .scroll-down{
    position: absolute;
    bottom: 3%;
    left: 50%;
    transform: translateX(-50%);
    span{
      display: block;
      color: #fff;
      text-transform: uppercase;
      font-weight: 700;
      letter-spacing: 1px;
      margin-bottom: 1.8rem;
      font-size: .8rem;
    }
    img{
      width: 30px;
    }
  }
}



.top-header-section{
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 60px;
  z-index: 70;

  .brand-logo{
    float: left;
    padding: 2rem;
    h1{
       @include headerReset();
    }
    .top-name{
      font-size: 1.8rem;
      transform: translateX(.3rem);
    }
    .bottom-name{
      @include curs();
      margin-top: -.8rem;
      letter-spacing: 1px;
    }
    @media (max-width: 550px) {
      margin-top: -1rem;
    }
  }
}


.gallery-wrap{
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999;
  height: 100%;
  width: 100%;
  background: purple;
}



.pro-alpha-slide{
   @include slideDefault();
   background: $brand-black;
   display: table;
   .pro-al__wrapper{
     display: table-cell;
     text-align: center;
     vertical-align: middle;
     h1{
       font-size: 15rem;
       color: #fff;
       text-transform: uppercase;
       position: relative;
     }
     .cover-slide{
       position: absolute;
       top: 50%;
       left: 50%;
       transform: translate(-50%, -50%);
       background: $brand-black;
       height: 300px;
       min-width: 800px;
     }
   }
   @media (max-width:550px) {
     h1{
       font-size: 8rem !important;
     }
   }
}



</style>