<template>
  <div id="app">
    <div class="cursor" ref="cursor"></div>
    <div class="cursor-follower" ref="follower"></div>
    <router-view/>
  </div>
</template>



<script>

import { TweenMax } from 'gsap'
import gsap from 'gsap'
import CSSRulePlugin from 'gsap/CSSRulePlugin'


export default {
  data(){
    return{
      
    }
  },
  methods:{

  },
  mounted(){
    gsap.registerPlugin(CSSRulePlugin);



      const {cursor} = this.$refs
      const {follower} = this.$refs

      let posX = 0,
          posY = 0;

      let mouseX = 0,
          mouseY = 0;

      TweenMax.to({}, 0.016, {
        repeat: -1,
        onRepeat: function() {
          posX += (mouseX - posX) / 9;
          posY += (mouseY - posY) / 9;

          TweenMax.set(follower, {
              css: {
              left: posX - 12,
              top: posY - 12
              }
          });

          TweenMax.set(cursor, {
              css: {
              left: mouseX,
              top: mouseY
              }
          });
        }
      });


      document.addEventListener('mousemove', (e) => {
         mouseX = e.clientX;
         mouseY = e.clientY;
      })
  },


}
</script>


<style lang="scss">
  @import 'assets/styles/_mixin.scss';
 

*{
  cursor: none;
}
*{
  box-sizing: border-box;
  text-decoration: none;
}
body{
  margin: 0;
  padding: 0;
  overflow-x: hidden;
    background: $brand-black;
}

.alpha-slider{
 @include slideDefault();
  transform: translateY(-100%);
}

.v-header{
  height: 100vh;
  display: flex;
  .fullscreen-video-wrap{
    @include fullScreenVideoWrap();
    video{
      min-height: 100%;
      min-width: 100%;
    }
  }
}
 
  // .brand-logo__bottom{
  //   margin-bottom: 2rem;
  //     h1{
  //          @include headerReset();
  //          margin-left: 2rem;
  //       }
  //       .top-name{
  //           font-size: 1.8rem;
  //           transform: translateX(.3rem);
  //       }
  //       .bottom-name{
  //           @include curs();
  //           margin-top: -.8rem;
  //           letter-spacing: 1px;
  //       }
  //   }
 .container{
    max-width: 960px;
    padding-left: 1rem;
    padding-right: 1rem;
    margin: 0;
}

 ::-webkit-scrollbar {
  width: 1em;
}
 
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.0);
}
 
::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, 0.0);
  outline: 1px solid rgba(0, 0, 0, 0.0);
}
  
  #app {
    margin: 0;
    padding: 0;
    font-family:  'Alata', sans-serif;
    font-weight: 300;
    cursor: none;


  }



  #nav{
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100%;
    margin: 0 auto;
    z-index: 999;
    overflow-y: scroll;
    overflow-x: hidden;
    background: darken(#262626, 5);
    transform: translateX(100%);
    .nav-wrapper{
      display: flex;
      width: 80%;
      margin: 0 auto;
      padding-top: 5%;
      .link-section{
        a{
          text-transform: uppercase;
          color: #fff;
          font-size: 8rem;
          display: block;
          letter-spacing: -4px;
          font-weight: bold;
          transition: all .3s ease-in-out;
          &:hover{
            color: $domantLink;
          }
        }
      }
      .video-link-case, .photo-link-case{
        max-width: 600px;
        transform: rotate(-5deg) translate(15%, 15%);
        background: #fff;
        padding: .5rem;
        video, img{
          width: 100%;
        }
      }
    }
    @media (max-width: 550px) {
      .nav-wrapper{
        .link-section{
          margin-top: 10%;
          a{
            font-size: 4rem;
          }
        }
        .video-link-case, .photo-link-case{
          display: none;
        }
      }
      
    }
    .bottom-nav__section{
      display: flex;
      justify-content: space-between;
      width: 80%;
      margin: 0 auto;
      padding-top: 2rem;
      .bottom-nav__blocks{
        flex-basis: 30%;
      }

      a{
        font-size: 1.1em;
        color: #fff;
        padding: 0 2rem;
        font-weight: 300;
        font-family: $headers;
        transition: all .3s ease-in-out;
        &:hover{
          color: #e9ab9d;
        }
      }
      @media (max-width:550px) {
        flex-direction: column;
        a{
          padding: 1rem 0;
          margin-right: 1rem;
          display: block;
        }
      }
    }
  }
    
  .humburg-menu{
      position: absolute;
      right: 0;
      top: 0;
      padding: 2rem;
      z-index: 999;
        span{
          display: block;
          height: 4px;
          width: 40px;
          background: #fff;
          opacity: .7;
          margin-bottom: 8px;
          transition: all .3s ease-in-out;
        }
         &:hover span{
            opacity: 1;
      }
      @media (max-width: 550px) {
        top: 0%;
      }
  }


.hovered{
  transform: scale(3);
}

  .cursor {
    position: fixed;
    background-color: #fff;
    width: 8px;
    height: 8px;
    z-index: 1;
    border-radius: 100%;
    transition: 0.3s cubic-bezier(0.75, -1.27, 0.3, 2.33) transform,
        0.2s cubic-bezier(0.75, -0.27, 0.3, 1.33) opacity;
    user-select: none;
    pointer-events: none;
    z-index: 10000;
    transform: scale(1);
}

.cursor-follower {
    position: fixed;
    border: 1px solid #fff;
    width: 38px;
    height: 38px;
    border-radius: 100%;
    z-index: 1;
    transition: 0.6s cubic-bezier(0.75, -1.27, 0.3, 2.33) transform,
        0.2s cubic-bezier(0.75, -0.27, 0.3, 1.33) opacity, 0.2s cubic-bezier(0.75, -0.27, 0.3, 1.33) background;
    user-select: none;
    pointer-events: none;
    z-index: 10000;
    transform: translate(2px, 2px);
    overflow: hidden;

}



@media (max-width: 550px) {
  .cursor, .cursor-follower{
    display: none;
  }
}


//VIDEOS // PHOTOS
.back-home{
    span{
        transform: translate(2.5rem, -2.1rem);
    }
    img{
        width: 30px;
        transition: all .3s ease-in-out;
    }
    @include  resizeIcons();
    &:hover img{
        transform: translateX(-.5rem);
    }
    @media (min-width: 550px) {
         transform: translateX(2rem);
    }
}

.about-me{
    span{
        transform: translate(-4.8rem, -2.1rem);
    }
    img{
        width: 30px;
        transition: all .3s ease-in-out;
    }
    @include  resizeIcons();
     &:hover img{
        transform: translateX(.5rem);
    }
}




</style>
