<template>
  <div class="about">
    
    <div class="about_header">
        <div  class="about_header_image" data-aos="fade-right"
        data-aos-delay="0"></div>
        <div class="text">
          <div class="title-line" data-aos="fade-left"
        data-aos-delay="2000" data-aos-duration="1000"></div>
          <h1  data-aos="fade-down" data-aos-delay="1200" >THE <span>TEAM</span></h1>
          <h4 data-aos="fade-left"
        data-aos-delay="100">ingrwf-08</h4>
          <p data-aos="fade-left"
            data-aos-delay="300">Lorem ipsum dolor sit amet consectetur adipisicing elit. Fuga, illum nam. Nam quis aliquid quasi, eum libero voluptas beatae, perspiciatis fugiat aperiam dignissimos obcaecati neque veritatis consequuntur nemo? Sapiente, harum!</p>
          <p data-aos="fade-left"
        data-aos-delay="500">Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque quia recusandae sequi aut ullam, obcaecati explicabo.</p>
          <p data-aos="fade-left"
        data-aos-delay="700">Lorem ipsum dolor sit amet consectetur adipisicing elit. Fuga, illum nam. Nam quis aliquid quasi, eum libero voluptas beatae, perspiciatis fugiat aperiam dignissimos obcaecati neque veritatis consequuntur nemo? Sapiente, harum!</p>
        </div>
       
    </div>

    <div
      class="about_contain paragraph"
      data-aos="fade-right"
      data-aos-delay="0"
      v-for="teamMate in teamMates"
      :key="teamMate.name"
    >
      <div class="about_contain__logo">
        <img :src="teamMate.img" alt="logo" />
      </div>
      <div
        class="about_contain__text"
        data-aos="fade-left"
        data-aos-delay="400"
        data-aos-duration="1500"
      >
        <div class="title-line"></div>
        <h2>{{ teamMate.name }}</h2>
        <p>{{ teamMate.text }}</p>
        <div class="social-item" >
          <a data-aos="fade-up" data-aos-delay="800" class="social-item" :href="teamMate.git" target="_blank"
            ><i class="fab fa-github-square"></i
          ></a>
          <a data-aos="fade-up" data-aos-delay="1000" class="social-item" :href="teamMate.linkedin" target="_blank"
            ><i class="fab fa-linkedin"></i
          ></a>
          <a v-if="teamMate.web" data-aos="fade-up" data-aos-delay="1200" class="social-item" :href="teamMate.web" target="_blank"
            ><i class="fas fa-at"></i
          ></a>
          <a v-if="teamMate.mail" data-aos="fade-up" data-aos-delay="1400" class="social-item" :href="teamMate.mail" target="_blank"
            ><i class="fas fa-paper-plane"></i></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import dataAbout from "../dataAbout.json";

export default {
  name: "about",
  data() {
    return {
      teamMates: dataAbout
    };
  },
};
</script>

<style lang="scss">
@import "../assets/main.scss";

.about {
  @media screen and (max-width: 1023px) and (min-width: 767px) {
    padding: 6rem 2rem 5rem 2rem;
  }
  @media screen and (max-width: 767px) {
    padding: 0;
  }
  position: relative;
  padding-top: 7rem;
  padding: 0 20%;
  background-color: White;
  overflow: hidden;
  height: calc(100% + 20rem);
  

  &_header{
    @media screen and (max-width: 767px){
      display: flex;
      flex-direction: column !important;
      align-items: flex-start;
      justify-content: flex-start;
      left:0%;
      //padding: 0;
      padding-bottom: 20rem;
      
    }
    @media screen and (max-width: 1023px) and (min-width: 767px) {
      display: flex;
      flex-direction: column !important;
      align-items: flex-start;
      justify-content: flex-start;
      left:0%;
      padding: 0;
      height: 100%;
    }
    position: relative;
    left:-30%;
    width: 150%;
    height: 60vh;
    //border: 2px solid red;
    display: flex;
    justify-content: center;
    z-index: 0;
    padding: 5rem 0 5rem 0;
    &_image{
      @media screen and (max-width: 767px){
      width: 300px !important;
      min-height: 300px !important;
      background-position: center;
      background-size: 100%; 
      margin-top: -5rem;
      position: relative;
      top: -10%;
      left: 0%;
      
      //z-index: 999;
     
    }
      @media screen and (max-width: 1023px) and (min-width: 767px) {
      width: 100%;
      height: 300px;
      background-position: center;
      background-size: contain; 
      position: relative;
      left: 10%;
      top: -10%;
    }
      height: auto;
      width: 1300px;
      background: url('https://www.kikk.be/2017/files/library/Sponsors/02_Founding-partners/04_Media-partners/03_Partners/05_Friends/03_Partners/Cepegra-%28square%29_logo.jpg') left center no-repeat;
      background-position: center; /* Center the image */
      background-repeat: no-repeat; /* Do not repeat the image */
      background-size: 80%; 
      
    }
    .text{
      @media screen and (max-width: 767px){
        left:0%;
      }
      @media screen and (max-width: 1023px) and (min-width: 767px) {
      
      left:0%;
      }
      height: 500px;
      position: relative;
      right: 6rem;
      z-index: 1;
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      h1{
        @media screen and (max-width: 767px){
        right: 0;
          margin-top: 0%;
          font-size: 3.7rem;
        }
        @media screen and (max-width: 1023px) and (min-width: 767px) {
          right: 0;
          margin-top: -30%;
        }
        color: white;
        position: relative;
        right: 23%;
        font-size: 5rem;
        text-shadow: 1px 5px 2px $secondary, 0 0 1em $primary, 0 0 0.2em $primary;
        span{
          text-shadow: 5px 5px $secondary;
          text-shadow: 1px 5px 2px $primary, 0 0 1em $secondary, 0 0 0.2em $secondary;
        }
      }
      h4{
        @media screen and (max-width: 767px){
          right: 0;
          
        }
        @media screen and (max-width: 1023px) and (min-width: 767px) {
          right: 0;
        }
        position: relative;
        right: 10%;
        color: $primary;
        font-size: 2rem;
        padding-bottom: 2rem;
      }
      p{
        @media screen and (max-width: 767px){
          width: 60%;
        }
        @media screen and (max-width: 1023px) and (min-width: 767px) {
          width: 60%;
      }
        width: 100%;
        padding-bottom: 1rem;
        font-size: 1.1rem;
        font-weight: 300;
        color: $secondary;
        
      }
      .title-line {
        @media screen and (max-width: 1023px) and (min-width: 767px) {
          display: none;
        }
        @media screen and (max-width: 767px) {
           display: none;
        }
        height: 2rem;
        width: 65%;
        border-bottom: 2px solid $primary;
        position: relative;
        top: 3rem;
        left: 15rem;
      }
    }
  }

  .paragraph {
    @media screen and (max-width: 1023px) and (min-width: 767px) {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: flex-start;
    }
    @media screen and (max-width: 767px) {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: flex-start;
      padding-bottom: 6rem;
    }
    display: flex;
    align-items: center;
    position: relative;
    padding-bottom: 10rem;
    z-index: 0;
    width: 100%;
  }

  &_contain {
    &__logo {
      @media screen and (max-width: 1023px) and (min-width: 767px) {
        padding-bottom: 2rem;
      }
      @media screen and (max-width: 767px) {
        padding-bottom: 2rem;
        //left: -2rem;
      }
      width: 250px;
      img {
        width: 75%;
      }
    }

    &__text {
      @media screen and (max-width: 1023px) and (min-width: 767px) {
        //position: relative;
      }
      @media screen and (max-width: 767px) {
        padding-left: 2rem;
        padding: 0;
        //margin-right: 5rem !important;
        width: 100%;
      }
      width: 100%;
      //padding: 0 3rem;
      //padding-left: 10rem;

      display: flex;
      flex-direction: column;

      .title-line {
        @media screen and (max-width: 767px) {
          top: 2.8rem;
        }
        height: 1rem;
        width: 100%;
        border-bottom: 1px solid $primary;
        position: relative;
        top: 2.5rem;
      }
      h2 {
        @media screen and (max-width: 767px) {
          font-size: 2.5rem;
        }
        width: 100%;
        margin: 0;
        padding-bottom: 2rem;
        color: $primary;
        font-size: 1.82rem;
        text-transform: uppercase;
      }
      p {
        font-size: 1.1rem;
        font-weight: 300;
        color: $secondary;
      }
      .social-item {
        color: $primary;
        font-size: 1.5rem;
        padding-right: 1rem;
        padding-top: 1.5rem;
      }
    }
  }
  &__becode {
    &__logo {
      display: flex;
      justify-content: center;
      padding-left: 1rem;
    }
  }
}
.about__mjm.paragraph {
  padding-bottom: 0;
}
</style>
