<template>
  <div class="about">
    
    <div class="about_header">
        <div  class="about_header_image" data-aos="fade-right"
        data-aos-delay="0"></div>
        <div class="text">
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
      >
        <div class="title-line"></div>
        <h2>{{ teamMate.name }}</h2>
        <p>{{ teamMate.text }}</p>
        <div class="social-item" data-aos="flip-down" data-aos-delay="600">
          <a class="social-item" :href="teamMate.git" target="_blank"
            ><i class="fab fa-github-square"></i
          ></a>
          <a class="social-item" :href="teamMate.linkedin" target="_blank"
            ><i class="fab fa-linkedin"></i
          ></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "about",
  data() {
    return {
      teamMates: [
        {
          img:
            "https://media-exp1.licdn.com/dms/image/C5603AQGADOu0AJNNGg/profile-displayphoto-shrink_200_200/0?e=1606953600&v=beta&t=efZl7epWM3hHjkLXgpCL3EQxGcSAK3_ljcwZmzM6pn0",
          name: "Jonathan Fauchoux",
          text:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Veniam quod ad, esse aliquid debitis quia vel rem eos ea et enim? Minus sequi inventore accusamus cumque non asperiores est blanditiis.",
          git: "https://github.com/JonathanFauchoux",
          linkedin: "https://www.linkedin.com/in/jonathan-fauchoux-62b069163/",
        },
        {
          img:
            "https://media-exp1.licdn.com/dms/image/C5603AQFMZpUqeS0VVQ/profile-displayphoto-shrink_200_200/0?e=1606953600&v=beta&t=nB-DpWDkDN7B9kRyDLh0IpRMjGXy62s5QKaf3wCTJIM",
          name: "Maud Gennart",
          text:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Veniam quod ad, esse aliquid debitis quia vel rem eos ea et enim? Minus cumque non asperiores est blanditiis.",
          git: "https://github.com/maud08",
          linkedin: "https://www.linkedin.com/in/maud-gennart-02028a54/",
        },
        {
          img:
            "https://media-exp1.licdn.com/dms/image/C4E03AQHNH9NBPBMcvw/profile-displayphoto-shrink_800_800/0?e=1606953600&v=beta&t=qTMjVMHibFskiMbmNFH9TGs0ftnd-zvtje-X2O5sIxo",
          name: "Quentin Vandevorst",
          text:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Veniam quod ad, esse aliquid debitis quia vel rem eos ea et enim? Minus cumque non asperiores est blanditiis.",
          git: "https://github.com/Survive95",
          linkedin: "https://www.linkedin.com/in/quentinvandevorst/",
        },
        {
          img:
            "https://media-exp1.licdn.com/dms/image/C4D03AQE52BHZYTuVWA/profile-displayphoto-shrink_200_200/0?e=1606953600&v=beta&t=b-6b5dyFifVuKOoBOcfAgX-dYkut_PpJScc-msSTsHg",
          name: "Joseph Prygiel",
          text:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Veniam quod ad, esse aliquid debitis quia vel rem eos ea et enim? Minus cumque non asperiores est blanditiis.",
          git: "https://github.com/Procaillass",
          linkedin: "https://www.linkedin.com/in/joseph-prygiel-7401b1171/",
        },
        {
          img:
            "https://media-exp1.licdn.com/dms/image/C4D03AQEgo-yDbhYyXA/profile-displayphoto-shrink_200_200/0?e=1606953600&v=beta&t=uZLG1Bpwi_g4ENAFQbOWlQNQYBsMS37szuhLa-Wawn8",
          name: "Mathieu Slaedts",
          text:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Veniam quod ad, esse aliquid debitis quia vel rem eos ea et enim? Minus cumque non asperiores est blanditiis.",
          git: "https://github.com/MathieuSlaedts",
          linkedin: "https://www.linkedin.com/in/mathieuslaedts/",
        },
        {
          img:
            "https://media-exp1.licdn.com/dms/image/C5603AQFZTrtb8CcKAg/profile-displayphoto-shrink_200_200/0?e=1606953600&v=beta&t=kS91cwmMK8LYtojDDZPPjpcjdAUupOexrjTbdi6szG4",
          name: "Marvyn Splingaire ",
          text:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Veniam quod ad, esse aliquid debitis quia vel rem eos ea et enim? Minus cumque non asperiores est blanditiis.",
          git: "https://github.com/Othior",
          linkedin: "https://www.linkedin.com/in/marvyn-splingaire-675849191/",
        },
      ],
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
  padding: 0 10%;
  background-color: White;
  
  height: calc(100% + 20rem);
  

  &_header{
    
    position: relative;
    left:-30%;
    width: 150%;
    //border: 2px solid red;
    display: flex;
    justify-content: center;
    z-index: 0;
    padding: 5rem 0 10rem 0;
    &_image{
      height: auto;
      width: 1000px;
      background: url('https://www.kikk.be/2017/files/library/Sponsors/02_Founding-partners/04_Media-partners/03_Partners/05_Friends/03_Partners/Cepegra-%28square%29_logo.jpg') left center no-repeat;
    
   
    background-position: left; /* Center the image */
    background-repeat: no-repeat; /* Do not repeat the image */
    background-size: cover; 
    }
    .text{
      height: 500px;
      width: 50%;
      position: relative;
      //right: -50%;
      z-index: 1;
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      h1{
        color: $primary;
        position: relative;
        right: 23%;
        font-size: 4rem;
        span{
          color: $secondary;
        }
      }
      h4{
        position: relative;
        right: 10%;
        color: $primary;
        font-size: 2rem;
        padding-bottom: 2rem;
      }
      p{
        width: 100%;
        padding-bottom: 1rem;
        font-size: 1.1rem;
        font-weight: 300;
        color: $secondary;
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
      //padding: 3rem;
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
