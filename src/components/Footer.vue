<template>
  <footer class="footer">
    <div class="color">
      <div class="social-link">
        <p><span>Jam</span>Racker © copyright 2020</p>
        <div>
        <a href="https://github.com/JonathanFauchoux/jamrackersite" target="_blank"><i class="fab fa-github-square"></i></a>
        <a href="mailto:jamracker@gmail.com" target="_blank"><i class="fas fa-envelope"></i></a>

        </div>
      </div>
    </div>
  </footer>
</template>

<script>

export default {
  name: 'Footer',
  components: {

  }
}
</script>

<style lang="scss">
$primary    : #159EDE;
$secondary  : #606060;

  .footer{
    @media screen and (max-width: 767px){
    width: 90vw;
  }
     position: relative;
    // bottom:-1px;
    // left: 0; 
    // z-index: 99999;
    
    width: 100%;
    // margin-top: 3rem;
    overflow-x: hidden;
    .color{
      z-index: 99999;;
      background-color: white;
      height: 3.5rem;
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      .social-link{
        @media screen and (max-width: 767px){
            align-items: center;
            justify-content: space-around;
              width: 100%;
          }
        @media screen and (max-width: 1023px) and (min-width: 767px){
          display: flex;
          justify-content: center;
          
       
          width: 100%;

          a:nth-child(1){
            margin:0;
          }
        }
        display: flex;
       
        justify-content: center;
        
        p{
          @media screen and (max-width: 767px){
            font-size: .9rem;
            
          }
          padding-top: .5rem;
          color :$secondary;
          font-size: 1rem;
          span{
            color: $primary;
            font-weight: 600;
          }
        }
        a{
           @media screen and (max-width: 767px){
            margin: 0 .5rem;
            
          }
         //
          color: $secondary;
          font-size: 1.5rem;
          margin-left: 2rem;
          transition: all .3s;
          &:hover{
            color: $primary;
          }
        }
      }
    }
  }

</style>
