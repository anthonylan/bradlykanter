<template>
    <div class="photos">
    <div class="top-video-contents">
        <router-link to="videos" class="back-home"> <img src="../assets/chevron.svg"> <span class="span-in-icon">see videos</span>  </router-link>
        <router-link to="/" class="brand-logo">
            <h1 class="top-name">Bradley</h1>
            <h1 class="bottom-name">Kanter</h1>
          </router-link>
          <router-link to="about" class="about-me"> <img src="../assets/chevron-r.svg"> <span class="span-in-icon">about me</span>  </router-link>
      </div> 
     <div id="photos">
         
           <img src="https://i.ibb.co/PGCxtVn/13.jpg">
        
       
          <img src="https://i.ibb.co/RbgjwZR/14.jpg">
     
       
          <img src="https://i.ibb.co/0MDmKZ1/18.jpg">
       
        
           <img src="https://i.ibb.co/3N5mYT7/16.jpg">
     
       
            <img src="https://i.ibb.co/LvQRZQz/19.jpg">
      
        
           <img src="https://i.ibb.co/qDR1k2p/20.jpg">
        
      
            <img src="https://i.ibb.co/9T4DNCf/05.jpg">
        
       
            <img src="https://i.ibb.co/Tt53Z9s/04.jpg">
      
        
           <img src="https://i.ibb.co/fYgc7cz/08.jpg">
       
        
           <img src="https://i.ibb.co/9ygpBsp/06.jpg">
   
     
          <img src="../assets/photos/aus/03.jpg">
     
       
          <img src="../assets/photos/aus/07.jpg">
     
      
           <img src="../assets/photos/aus/09.jpg">
        <img src="../assets/photos/aus/10.jpg">
     
          <img src="../assets/photos/aus/11.jpg">
      
        
         <img src="../assets/photos/aus/12.jpg">
      
      
           <img src="../assets/photos/aus/15.jpg">
     
      
       <img src="../assets/photos/aus/17.jpg">
     
      
         <img src="../assets/photos/aus/01.jpg">
      
  
           <img src="../assets/photos/aus/02.jpg">
     
      
         <img src="https://i.ibb.co/wRKhmpH/01.jpg">
   
     
          <img src="https://i.ibb.co/cwVK0fJ/02.jpg">
   
     
          <img src="https://i.ibb.co/fnMmpwf/03.jpg">
      
       
         <img src="https://i.ibb.co/19DWZh2/04.jpg">
    
     
           <img src="https://i.ibb.co/WHXQC3W/05.jpg">
     
       
         <img src="https://i.ibb.co/HYTkvSF/06.jpg">
      
      
           <img src="https://i.ibb.co/7kcXz6w/07.jpg">
    
      
        <img src="https://i.ibb.co/Rbp2ntG/08.jpg">
    
     
        <img src="https://i.ibb.co/TPyqSPk/09.jpg">
     
      
      <img src="https://i.ibb.co/McWJm3s/10.jpg">
      
      
           <img src="https://i.ibb.co/GCcKvNt/11.jpg">
      
        
         <img src="https://i.ibb.co/zHTGJcp/12.jpg">
        
    </div> 
      <div class="lets-talk">
        <a href="https://www.instagram.com/panabrad" target="_blank" class="social">Instagram</a>
        <a href="https://www.linkedin.com/in/bradleykanter" target="_blank" class="social">linkedin</a>
        <a href="mailto:bradley.kanter@gmail.com" class="mail">let's talk!</a>
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
    mounted(){
        TweenMax.to('.alpha-slider', .5, {y: 0, ease: Expo.easeInOut})
          setTimeout(() => {
                TweenMax.to('.alpha-slider', .5, {y: '-100%', ease: Expo.easeInOut})
            }, 9000)

            // this.$el.querySelectorAll('#photos img').forEach((img) => {
            //   img.addEventListener('click', () => {
                
            //     if(img.classList.contains('full')){
            //       img.className = ''
            //     } else {
            //       img.className = 'full'
            //     }
                
            //   })
              
            // }) 

    }
}
</script>


<style lang="scss" scoped>
@import '../assets/styles/_mixin.scss';
.photos{
  margin-left: 1%;
}

#photos {
  /* Prevent vertical gaps */
  line-height: 0;
   
  -webkit-column-count: 3;
  -webkit-column-gap:   0px;
  -moz-column-count:    3;
  -moz-column-gap:      0px;
  column-count:         3;
  column-gap:           0px;  
}

#photos img {
  /* Just in case there are inline attributes */
  width: 100% !important;
  height: auto !important;
}


@media (max-width: 1200px) {
  #photos {
  -moz-column-count:    4;
  -webkit-column-count: 4;
  column-count:         4;
  }
}
@media (max-width: 1000px) {
  #photos {
  -moz-column-count:    3;
  -webkit-column-count: 3;
  column-count:         3;
  }
}
@media (max-width: 800px) {
  #photos {
  -moz-column-count:    2;
  -webkit-column-count: 2;
  column-count:         2;
  }
}
@media (max-width: 400px) {
  #photos {
  -moz-column-count:    1;
  -webkit-column-count: 1;
  column-count:         1;
  }
}


.full {
  position: fixed !important;
  left: 0%;
  top: 0;
  width: 100% !important;
  height: 100% !important;
  z-index: 100 !important;
}


.top-video-contents{
    display: flex;
    justify-content: space-between;
    padding-top: 2rem;
}



.span-in-icon{
 @include spanInicon();
}




 .brand-logo{
   @include logoDarkBg();
}
.lets-talk{
 @include letsTalk();
}




</sty