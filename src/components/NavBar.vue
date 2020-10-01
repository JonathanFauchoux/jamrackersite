<template>
  <div class="container">
    <nav class="navbar" :class="{ change : isActive }" @click=" isActive = !isActive">
      <div class="burger-menu">
        <div class="line line-1"></div>
        <div class="line line-2"></div>
        <div class="line line-3"></div>
      </div>
 
      <ul class="nav-list">
        <div class="logo">
          <img src="../assets/jamrackerLogo.jpg" alt="logo">
        </div>
        <router-link to="/" tag="li"  active-class="active" exact class="nav-item"><a class="nav-link">JamRacker</a></router-link>
        <router-link to="/About" tag="li"  active-class="active" exact class="nav-item"><a class="nav-link">Our Team</a></router-link>
        <router-link to="/Contact" tag="li" active-class="active" class="nav-item"><a class="nav-link">Contact</a></router-link>
      </ul>
    </nav>
    
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  data : () => {
    return {
      navbar : document.querySelector('.navbar'),
      isActive: true,
      
    }
  },
  methods:{
    
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" >
@import '../assets/main.scss';

.navbar{
  z-index: 99999;
  width: 100%;
  height: 100vh;
  background-color: white !important;
  margin-bottom: 3rem !important;
  position: fixed;
  top:0%;
  overflow: hidden;

  right: -100%;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  transition: right .8s cubic-bezier(1,0,0,1);
  
}

/* Burgerrr */
  .burger-menu{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    width: 30px;
    height: 25px;
    
    position: fixed;
    top: 1rem;
    right: 1rem;
    cursor: pointer;
  }
  .line{
    width: 100%;
    height: 3px;
    background-color: $primary;
    transition: all .6s ;
  }
  .change{
    right: 0;
  }
  .change .line-1{
    transform: rotateZ(-405deg) translate(-7px, 6px);
  }
  .change .line-2{
    opacity: 0;
  }
  .change .line-3{
    transform: rotateZ(405deg) translate(-5px, -6px);
  }
/* nav */
  .logo{
    
    img{
    object-fit: contain;
    width: 50% !important;
    }
    
  }

  .nav-list{
    text-align: center;
    width: 100%;
    padding: 0rem 3rem;
  }
  .nav-item{
    display: flex;
    list-style: none;
    margin: 1.7rem 0;
    min-width: 100%;
    
    
  }
  .nav-link{
    text-decoration: none;
    width: 100%;
    font-size: 14px;
    text-transform: uppercase;
    color: $secondary !important;
    font-weight: 300;
    position: relative;
    padding: 10px 0;
  }
  .nav-link::before, .nav-link::after {
    content: "";
    width: 50%;
    height: 2px;
    background-color: $primary !important;
    position: absolute;
    left:25%;
    transform: scaleX(0) ;
    transition: all 0.5s;
  }
  .nav-link::after{
    bottom: 0;
    transform-origin: right;
  }
  .nav-link::before{
    top: 0;
    transform-origin: left;
  }
  .nav-link:hover{
    color: $secondary;
    
  }
  .nav-link:hover::before, .nav-link:hover::after {
    transform: scaleX(1) ;
  }
  .active>a{
    //background: red;
    color: $primary !important;
    max-width: 100%;
  }
   @media screen and (min-width: 768px) {
  .navbar{
  z-index: 9999;
  width: 100%;
  height: 3.5rem;
  background-color:black;
  position: fixed;
  
  left:0;
  display: flex;
  
  justify-content: flex-start;
  align-items: center;
  border-radius: 0 0 0 0;
  transition: all .5s;
}
  .logo{
    position: absolute;
    top: .3rem;
    left: 3rem;
    text-align: start;
    height: 100%;
    
    img{
    object-fit: contain;
    width: 33% !important;
    }
    
  }
  .burger-menu {
    display: none;
  }
  .nav-list{
    display: flex;
    justify-content: flex-end;
    height: 100%;

    align-items: center;
    padding-right: 10rem;
    
   
  }
  .nav-item{
    
    
    list-style: none;
    margin: 0 1rem;
    min-width: 3rem;
    
    
  }
  .nav-link{
    display: flex;
    justify-content: center;
    text-decoration: none;
    width: 100%;
    font-size: .8rem;
    text-transform: uppercase;
    color: white;
    font-weight: 300;
    position: relative;
    padding: 10px;
  }
  .nav-link::before, .nav-link::after {
    content: "";
    width: 100%;
    height: 2px;
    background-color: white;
    position: absolute;
    left:0;
    transform: scaleX(0) ;
    transition: all 0.5s;
  }
}
</style>