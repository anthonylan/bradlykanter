<template>
  <div class="about">
    <router-link to="/" class="return"> <img src="../assets/chevron.svg"><span> Return to home</span></router-link>
    <div class="about-image">
      <img src="../assets/photos/pro01.jpg">
    </div>
    <div class="contents-about">
      <h1 class="ml13">Creative Producer + Director of Photography.</h1>
      <h1 class="ml14">As long as I can remember, I have been pursuing not just a career in video production and filmmaking but a life dedicated to telling stories through compelling images.</h1>

      <div class="inner-content__container">
         <p>After graduating from Columbia College Chicago with a BA in filmmaking and entertainment business, I have been fortunate to travel the country working in myriad roles in Hollywood features, prestige television shows, branded content for Fortune 500 companies, and live streaming premiere music festivals.</p>
          <p>In 2017, I combined two of my major passions of animals and video, when I joined Chewy.com as a Creative Producer. Since then, I have helped to build a video studio, managed multiple creative pivots and oversaw the production of nearly 10,000 videos.</p>
         <p>When I’m not hiking, rock climbing, or at the movie theater, I can be found spending quality time with my two crazy dogs and my beautiful partner. My travels have brought me to the Carribean Islands, Cuba, and Australia where I’ve documented the incredible beauty of our planet.</p>
      </div>
    </div>

    <div class="brands">
      <div class="brand-parent br-pt">
        <div class="brand-children">
          <img src="../assets/photos/brands/iro.png">
        </div>
          <div class="brand-children br-mid">
          <img src="../assets/photos/brands/fox.png">
        </div>
          <div class="brand-children">
          <img src="../assets/photos/brands/vice.png">
        </div>
      </div>
       <div class="brand-parent br-alt">
        <div class="brand-children">
          <img src="../assets/photos/brands/brow.jpg">
        </div>
          <div class="brand-children br-mid">
          <img src="../assets/photos/brands/digocean.png">
        </div>
          <div class="brand-children">
          <img src="../assets/photos/brands/warner.png">
        </div>
      </div>    
    </div> 

    <div class="recognition">
      <div class="wrapper">
        <div class="block sm-br">
          <h2>recognition</h2>
        </div>
        <div class="block lg-br">
          <h3>2014 DV Award <span> —The Black & White Years</span> </h3>
           <h3>Best Cinematography <span> —Mortal Dilemma</span> </h3>
        </div>
      </div>
    </div>

<div class="lets-talk">
  <a href="https://www.instagram.com/panabrad" target="_blank" class="social">Instagram</a>
  <a href="https://www.linkedin.com/in/bradleykanter" target="_blank" class="social">linkedin</a>
  <a href="mailto:bradley.kanter@gmail.com" class="mail">let's talk!</a>
</div>




<div class="alpha-slider"></div>
  </div>
</template>


<script>
import anime  from 'animejs'
import { TweenMax } from 'gsap'
import { Expo } from 'gsap'



// import AOS from 'aos'
// import 'aos/dist/aos.css'

export default {
  data(){
    return{

    }
  },
  mounted(){

  // Wrap every letter in a span
let textWrapper = document.querySelector('.ml13');
textWrapper.innerHTML = textWrapper.textContent.replace(/\S/g, "<span class='letter'>$&</span>");

let textWrapper2 = document.querySelector('.ml14');
textWrapper2.innerHTML = textWrapper2.textContent.replace(/\S/g, "<span class='letter'>$&</span>");



//anime.timeline({loop: true})
setTimeout(() => {
   anime({
    targets: '.ml13 .letter',
    translateY: [100,0],
    translateZ: 0,
    opacity: [0,1],
    easing: "easeOutExpo",
    duration: 1400,
    delay: (el, i) => 300 + 30 * i
  })

  anime({
    targets: '.ml14 .letter',
    translateY: [100,0],
    translateZ: 0,
    opacity: [0,1],
    easing: "easeOutExpo",
    duration: 1400,
    delay: (el, i) => 2000 + 30 * i
  })
}, 1000)



     TweenMax.to('.alpha-slider', .5, {y: 0, ease: Expo.easeInOut})
      setTimeout(() => {
          TweenMax.to('.alpha-slider', .5, {y: '-100%', ease: Expo.easeInOut})
      }, 1000)


      //TweenMax.to('.contents-about', .5, {skewY:-5, compensated:true, yoyo:true, ease:Linear.easeNone});

     // AOS.init()
  }
}
</script>


<style lang="scss" scoped>


@import '../assets/styles/_mixin.scss';

@import url('https://fonts.googleapis.com/css?family=Kumar+One+Outline&display=swap');

$gray: #747474;

.return{
  position: absolute;
  top: 0;
  left: 0;
  color: #fff;
  z-index: 10;
  padding: 2rem;
  img{
    width: 20px;
  }
  span{
    display: inline-block;
    position: relative;
    top: -.2rem;
    left: .5rem;
    &::before{
      content: '';
      position: absolute;
      left: 0;
      bottom: 0%;
      width: 0%;
      height: 2px;
      background: #fff;
      transition: all .2s ease-in-out;
    }
    &:hover::before{
      width: 100%;
    }
     &:hover img{
      opacity: 0;
    }
  }
}

.brands{
  background: #fff;
  width: 100%;
  margin-top: 4rem;

  .brand-parent{
    display: flex;
    justify-content: center;
    width: 100%;
    .brand-children{
      flex-basis: 33%;
      text-align: center;
      padding: 5rem 0;
      img{
        width: 120px;
        margin: 0 auto;
        transition: all .3s ease-in-out;
        &:hover{
          opacity: .6;
        }
      }
    }
   .br-mid{
     border-right: 1px solid lighten($gray, 30);
     border-left: 1px solid lighten($gray, 30);
   }

  }
   .br-pt{
     padding: 4rem 4rem 0 4rem;
     .brand-children{
        border-bottom: 1px solid lighten($gray, 30);
     }
   }
    .br-alt{
     padding: 0rem 4rem 4rem 4rem;
   }

   @media (max-width: 550px) {
     .brand-parent{
       flex-direction: column;
       padding: 1rem;
       .brand-children{
         padding: 2rem 0;
         border: none;
       }
       img{
         width: 50px !important;
       }
     }
   }
}


.recognition{
  padding: 2rem 0 0 0;
  .wrapper{
    width: 60%;
    margin: 1rem auto;
    display: flex;
    justify-content:left;
    h2{
      color: $gray;
      text-transform: uppercase;
    }
    h3{
      color: #fff;
      font-family: $headers;
      font-weight: 300;
    }
    .lg-br{
       border-bottom: 1px solid darken($gray, 20);
       padding-left: 3rem;
       flex-basis: 70%;
    }
  }
  .sm-br{
    flex-basis: 30%;
  }
  @media (max-width: 550px) {
    .wrapper{
      flex-direction: column;
      .lg-br{
        padding-left: 0;
      }
    }
  }
}



.lets-talk{
 @include letsTalk();
}



.ml13 .letter, .ml14 .letter {
  display: inline-block;
  line-height: 1em;
}



.about{
  background: darken(#262626, 5);
  padding: 4rem 0;
  overflow-x: hidden;
  .about-image{
    width: 600px;
    margin: 0 auto;
    text-align: center;
    transform: rotate(-5deg);
    transition: all .3s ease-in-out;
    img{
      width: 100%;
    }
  }

  .contents-about{
    width: 60%;
    margin: 0 auto;
    h1{
      color: #fff;
      font-family: $headers;
      font-size: 3.5rem;
      line-height: 1.6;
      font-weight: 400;
    }
    .inner-content__container{
      width: 70%;
      margin: 0 auto;
    }
    p{
      color: #fff;
      font-weight: 300;
      font-size: 1.2rem;
      line-height: 1.5;
      font-family: $headers;
    }
  }

  @media (max-width: 550px) {
    .contents-about{
      width: 90%;
      h1{
        font-size: 1.5rem;
      }
      .inner-content__container{
        width: 80%;
      }
      p{
      font-size: 1rem;
    }
    }
    .about-image{
      transform: translateX(-20%) rotate(-4deg);
      margin-bottom: 2rem;
      img{
        width: 300px;
      }
    }
  }
}

</style>