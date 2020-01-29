<template>
    <div class="videos">
       <div class="video-wrapper">
           <div class="top-video-contents">
           <router-link to="/" class="back-home"> <img src="../assets/chevron.svg"> <span class="span-in-icon">go back</span>  </router-link>
            <router-link to="/" class="brand-logo">
                <h1 class="top-name">Bradley</h1>
                <h1 class="bottom-name">Kanter</h1>
             </router-link>
             <router-link to="about" class="about-me"> <img src="../assets/chevron-r.svg"> <span class="span-in-icon">about me</span>  </router-link>
           </div>
           <div class="notice" ref="note">
               <p class="hide-om">Double click to exit</p>
               <p class="hide-od">Click on video to exit</p>
           </div>
           <div class="inner-flex">
               <div class="blocks">
                   <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Music</h4>
                           <h2>Bullet For My Valentine</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/bullet.mp4" autoplay loop="false" muted></video>
               </div>
                <div class="blocks">
                     <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Music</h4>
                           <h2>Black & White</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/blacknwhite.mp4"  loop="false" autoplay muted></video>
               </div>
           </div>
            <div class="inner-flex">
               <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Music</h4>
                           <h2>Midnight Empire</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/midnightempire.mp4" autoplay loop="false" muted></video>
               </div>
                <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Narrative</h4>
                           <h2>Mortal Dilemma</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/mortal.mp4" autoplay  loop="false" muted></video>
               </div>
           </div>
          <div class="inner-flex">
               <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Narrative</h4>
                           <h2>The gate</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/thegate.mp4" autoplay loop="false" muted></video>
               </div>
                <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Brand</h4>
                           <h2>Dog thoughts</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/dogthought.mp4" autoplay  loop="false" muted></video>
               </div>
           </div>
          <!-- <div class="inner-flex">
               <div class="blocks extra-refs">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Brand</h4>
                           <h2>Bon Apetite</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/bonone.mp4" autoplay loop="false" ref="bon" muted></video>
               </div>
                <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Brand</h4>
                           <h2>Bon Apetite</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/bontwo.mp4" autoplay  loop="false" muted></video>
               </div>
           </div> -->
            <div class="inner-flex">
               <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Brand</h4>
                           <h2>iro dallas</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/dallas.mp4" autoplay loop="false" muted></video>
               </div>
                <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Brand</h4>
                           <h2>Chewy</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/training.mp4" autoplay  loop="false" muted></video>
               </div>
           </div>
              <div class="inner-flex">
               <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Brand</h4>
                           <h2>Greenpeace</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/greenpeace.mp4" autoplay loop="false" muted></video>
               </div>
                <div class="blocks">
                    <div class="block-overlay">
                       <div class="meta-d">
                           <h4>Collections</h4>
                           <h2>Reel</h2>
                       </div>
                       <div class="play-control"> <span></span> </div>
                   </div>
                   <video src="../assets/videos/reel2015.mp4" autoplay  loop="false" muted></video>
               </div>
           </div>
       </div>


<!-- <div class="extra-video">
     <video src="../assets/videos/bontwo.mp4" loop="false" muted></video>
</div> -->

                <div class="lets-talk">
                    <router-link to="photos" class="mail">see photos</router-link>
                </div>
                <div class="alpha-slider">
                    
                </div>
          
    </div>
</template>



<script>
import { TweenMax } from 'gsap'
import { Expo } from 'gsap'


export default {
    data(){
       return{

       }
    },
    methods:{

    },
    mounted(){
        document.querySelectorAll('video').forEach((vid) => {
            vid.addEventListener('loadedmetadata', () => {
                setTimeout(() => {
                    vid.pause()
                     TweenMax.to('.alpha-slider', .5, {y: '-100%', ease: Expo.easeInOut})
                }, 3000)
            })
        })


    //  const pEl = document.querySelector('.video-wrapper')
        this.$el.querySelectorAll('.blocks').forEach((el) => {

            if(!/Android|webOS|iPhone|iPad|iPod|BlackBerry/i.test(navigator.userAgent)){
                    el.addEventListener('click', () => {
                        el.classList.add('full')
                        el.querySelector('video').play()
                        el.querySelector('video').muted = !el.querySelector('video').muted
                        TweenMax.to('.notice', 1, {marginTop: 0})
                    })

                    el.addEventListener('dblclick', () => {
                        el.classList.remove('full')
                        el.querySelector('video').pause()
                        TweenMax.to('.notice', 1, {marginTop: '-100%'})
                    })
            }



        //Detect Mobile

           if( /Android|webOS|iPhone|iPad|iPod|BlackBerry/i.test(navigator.userAgent) ) {

                   el.querySelector('.block-overlay').addEventListener('click', () => {
                     if(el.classList.contains('full')){
                         console.log('..being playing');
                            el.classList.remove('full')
                            el.querySelector('video').pause()
                            TweenMax.to('.notice', 1, {marginTop: '-100%'})
                         
                     }else{
                          console.log('..just started')
                           el.classList.add('full')
                            el.querySelector('video').play()
                            TweenMax.to('.notice', 1, {marginTop: 0})
                     }
                       
                   })
          
                    
          }
          
        })

   
        TweenMax.to('.alpha-slider', .5, {y: 0, ease: Expo.easeInOut})
        // const { bon } = this.$refs;
       
        // bon.currentTime = 510;
        //  const elExtra =  document.querySelector('.extra-video')

    //   let timer = setInterval(() => {
    //       if(bon.currentTime >= 522){
    //           bon.pause()
    //           elExtra.style.display = 'block'
    //           elExtra.querySelector('video').play()
    //           document.querySelector('.extra-refs').classList.remove()
    //          setTimeout(() => {
    //              clearInterval(timer)
    //          }, 800)
    //       }
    //   }, 1000)

    //   elExtra.addEventListener('dblclick', () => {
    //       elExtra.style.display = 'none'
    //   })

    }
}
</script>


<style lang="scss">
@import '../assets/styles/_mixin.scss';



.extra-video{
    display: none;
    video{
        width: 100%;
    }
}


.top-video-contents{
    display: flex;
    justify-content: space-between;
}

.span-in-icon{
   @include spanInicon();
}



.videos{
    background: $brand-black;
    padding: 5% 0;
    margin: 0;

    .video-wrapper{
        width: 95%;
        margin: 0 auto;

        .inner-flex{
            display: flex;
            margin-top: -1%;
            justify-content: center;
            .blocks{
                flex-basis: 50%;
                position: relative;
                //z-index: 10;
                .block-overlay{
                    position: absolute;
                    top: 0;
                    left: 0;
                    height: 100%;
                    width: 100%;
                    color: #fff;
                    z-index: 2;
                    .meta-d{
                        margin-left: 1rem;
                    }
                    h4{
                        font-weight: 400;
                    }
                    h2{
                        text-transform: uppercase;
                        margin: 0;
                        margin-top: -1rem;
                        font-size: 1.6rem;
                        word-spacing: -2px;
                    }
                    .play-control{
                        background: #fff;
                        height: 90px;
                        width: 90px;
                        border-radius: 100%;
                        position: absolute;
                        left: 50%;
                        top: 50%;
                        transform: translate(-50%, -50%);
                        opacity: 0;
                        transition: all .3s ease-in-out;
                        span{
                            display: block;
                            @include play();
                             border-color: transparent transparent transparent $brand-black;
                             position: absolute;
                             left: 50%;
                             top: 50%;
                             transform: translate(-50%, -50%);
                        }
                    }
                   @media (max-width: 550px) {
                       h2{
                           font-size: .9rem;
                       }
                       .play-control{
                           display: none;
                       }
                   }
                }
                video{
                    width: 100%;
                }
            }
            @media (max-width: 550px) {
                flex-direction: column;
            }
        }
    }
}

  .brand-logo{
     @include logoDarkBg();
  }

@media (max-width: 550px){
        .hide-om{
        display: none;
    }
}
@media (min-width: 550px){
        .hide-od{
         display:none;
    }
}

.hidden{
    display: none;
}


.block-overlay:hover .play-control{
    opacity: 1 !important;
}


.full {
  position: fixed !important;
  left: 0;
  top: 0;
  width: 100% !important;
  height: 100% !important;
  z-index: 100 !important;
  @media (max-width:550px) {
      video{
          height: 100vh !important;
      }
  }
}

.notice{
    position: fixed;
    top: 0;
    left: 50%;
    height: 50px;
    width: 200px;
    background: rgba(27, 9, 9, 0.5);
    transform: translateX(-50%);
    z-index: 9999;
    padding: 0 1rem;
    border-radius: 4px;
    padding-bottom: 1rem;
    margin-top: -100%;
    text-align: center;
    p{
        color: #fff;
    }
}

.lets-talk{
 @include letsTalk();
}
</style>