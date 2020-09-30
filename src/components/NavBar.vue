<template>
  <div class="container">
    <nav class="navbar" :class="{ change : isActive }" @click=" isActive = !isActive">
      <div class="burger-menu">
        <div class="line line-1"></div>
        <div class="line line-2"></div>
        <div class="line line-3"></div>
      </div>
 
      <ul class="nav-list">
        <div class="logo">Logo</div>
        <router-link to="/" tag="li"  active-class="active" exact class="nav-item"><a class="nav-link">Home</a></router-link>
        <router-link to="/About" tag="li"  active-class="active" exact class="nav-item"><a class="nav-link">About</a></router-link>
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
$primary    : #e471ff;
$secondary  : #4AE4FF;
$ground : #c9ff4c;


.navbar{
  z-index: 99999;
  width: 100%;
  height: 100vh;
  background-color: black;
  margin-bottom: 3rem !important;
  position: fixed;
  top:0%;

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
  .nav-list{
    text-align: center;
    width: 100%;
    padding: 0rem 3rem;
  }
  .nav-item{
    display: flex;
    list-style: none;
    margin: 1rem 0;
    min-width: 100%;
    
    
  }
  .nav-link{
    text-decoration: none;
    width: 100%;
    font-size: 1.75rem;
    text-transform: uppercase;
    color: white;
    font-weight: 300;
    position: relative;
    padding: 3px 0;
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
    background: white;
    color: $primary;
    
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
  transition: right .8s cubic-bezier(1,0,0,1);
  box-shadow: 3px 5px 20px 2px rgba(0, 0, 0, 0.5);
}
  .logo{
    position: absolute;
    top: .3rem;
    left: 3rem;
   
    height: 100%;
    width: 100px;
    img{
    object-fit: contain;
    }
    
  }
  .burger-menu {
    display: none;
  }
  .nav-list{
    display: flex;
    justify-content: flex-end;

    align-items: center;
    padding-right: 15rem;
    
   
  }
  .nav-item{
    width: 10%;
    
    list-style: none;
    margin: 1rem ;
    min-width: 7.5rem;
    
    
  }
  .nav-link{
    display: flex;
    justify-content: center;
    text-decoration: none;
    width: 100%;
    font-size: 1.2rem;
    text-transform: uppercase;
    color: white;
    font-weight: 300;
    position: relative;
    padding: 3px 0;
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