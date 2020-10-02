<template>
  <div class="contact">
  <div class="card" >
    <figure class="front" @click="toggleClass()" >
      <img src="https://images.unsplash.com/photo-1459233313842-cd392ee2c388?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=500&q=60" alt="front">
      <div class="caption">
        <img class="contact_logo" src="../assets/jamrackerLogo.png" alt="">
        <h2 v-if="dataForm.name == null" >Contact <span>Us</span></h2>  
        <div class="msgSent" v-if="dataForm.email">
          <h3>Dear, {{dataForm.name}}</h3>
          <p><span>Subject :</span> {{this.dataForm.subject}}</p>
          <p><span>Your message :</span> {{this.dataForm.message}}</p>
          <p class="sent"><span>Has been sent!</span></p>
        </div>
        
      </div>			
    </figure>

    <figure  class="back">
       <img src="https://images.unsplash.com/photo-1519677584237-752f8853252e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80" alt="back">
        <div class="caption">
         <Form @updateDataForm="updateDataForm"/>
        </div>
    </figure>
  </div>
</div>
</template>

<script>
import Form from '../components/Form'

export default {
  name: "Contact",
  components:{
    Form
  },
  data() {
    return {
      dataForm: {},
    };
  },
  methods:{
    toggleClass(){
      this.toggle =!this.toggle
      let card = document.querySelector('.card')
      if(card.classList.contains('flipped')){return}
      else{card.classList.add('flipped')}
    },
    updateDataForm(form){
      this.dataForm = form
    }
  },
  beforeMount(){
   window.scroll(0,0)      
  }
};
</script>

<style lang="scss">
@import "../assets/main.scss";
.msgSent{
  @media screen and (max-width: 767px){
    width: 70%;
    top: 50%;
  }
  position: absolute;
  left: 5%;
  top: 30%;
  text-align: start;
  color: $secondary;
  width: 50%;
  h3{
    @media screen and (max-width: 767px){
      position: relative;
      top: -15rem;
      font-size: 1.2rem;
    }
    padding-bottom: 1.5rem;
  }
  p{
    @media screen and (max-width: 767px){
      font-size: 1rem;
    }
    color: $secondary;
    padding: .5rem 0;
    span{
      color: $primary;
    }
  }
  .sent{
    font-size: 2rem;
    font-weight: 600;
  }
}
.contact, figure{
  @media screen and (max-width: 767px) {
    width: 90vw;
  }
  width: 80vw;
  height: 700px;
 
}

.contact{
  
  @media screen and (max-width: 1023px) and (min-width: 767px) {
    padding: 6rem 2rem 5rem 2rem;
  }
  @media screen and (max-width: 767px) {
    padding: 0;
    margin-left: 0 !important;
  }
  position: relative;
  perspective:1000;
  padding-top: 7rem;
  padding: 6% 10%;
  background-color: White;
  overflow: hidden;
  &_logo{
    @media screen and (max-width: 767px){
      width: 55%;
      top: -45%;
    }
    position: absolute;
    top: -39%;
    left: 5%;
    width: 30%;
    object-fit: contain;
    margin: 0;
  }
 
}

.card{
  width: 100%;
  position: relative;
  transition: 0.6s;
  transform-style: preserve-3d;
}

figure{
  background: $secondary;
  color: #fff;
  backface-visibility: hidden;
  overflow: hidden;
  position: absolute;
  top: 0;
  left: 0;
  text-align: center;
  
  
}

figure.front,  figure.back{
  transform: rotateY(0deg);
  z-index: 2;
  display: flex;
  flex-direction: column;

  cursor: pointer;
  transition: 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 1px 5px rgba(0,0,0,0.9);
}

figure.back,
.card.flipped{
  transform: rotateY(180deg);
  cursor: default;
}

figure img{
  @media screen and (max-width: 767px){
      object-fit: cover;
      margin-left: -20rem;
  }
  position: relative;
  object-fit: cover;
 // display: block;
  min-height: 100%;
  //opacity: 0.7;
}

figure .caption {
  @media screen and (max-width: 767px){
    padding: 2rem 0 !important;
  }
  position: absolute;
  top: 0;
  left: 0;
  width: 94%;
  height: 100%;
  
  padding: 2em;
  //backface-visibility: hidden;
}

.front .caption{
  font-size: 1.25em;
}

.front .caption:before {
  @media screen and (max-width: 768px){
  display: none;
  }
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(rgba(72,76,97,0) 0%, rgba($primary,0.8) 75%);
  content: '';
  opacity: 0;
  transform: translate3d(0,50%,0);
  transition: opacity 0.35s, transform 0.35s;
}


.front:hover .caption:before{
  
  opacity: 1;
  transform: translate3d(0,0,0);
}

.front h2{
  @media screen and (max-width: 768px){
    font-size: 2rem;
    right: 15%;
    top: 60%;
  }
  word-spacing: 0.15em;
  font-weight: 300;
  font-size: 2.6em;
  position: absolute;
  text-transform: uppercase;
  top: 50%;
  right: 30%;
  width: 100%;
  color: $secondary;
  transition: transform 0.35s, color 0.35s;
  transform: translate3d(0,-50%,0);
}

.front h2 span {
  font-weight: bold;
  color: $primary;
  
}


.front h2:after{
  position: absolute;
  bottom: -10px;
  left: 70px;
  right: 70px;
  height: 2px;
  background: #fff;
  content: '';
  transition: transform 0.35s;
  transform: translate3d(-130%,0,0);
}

.front:hover h2 {
  color: #fff;
  -webkit-transform: translate3d(0,-50%,0) translate3d(0,-40px,0);
  transform: translate3d(0,-50%,0) translate3d(0,-40px,0);
}
.front:hover h2 span{
  text-shadow: 0px 0px 8px white;
}
.front:hover h2:after {
  transform: translate3d(0,0,0);
}



.card.flipped .back .caption:before,
.card.flipped .back .caption:after {
  opacity: .9;
  transform: scale(1);  
}





</style>