<template>
  <footer class="footer">
    <div class="color">
      <div class="social-link">
        <p>© copyright 2020 JamRacker</p>
        <a href="https://github.com/JonathanFauchoux" target="_blank"><i class="fab fa-github-square"></i></a>
        <a href="mailto:jonathan.fauchoux@gmail.com" target="_blank"><i class="fas fa-envelope"></i></a>
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

$primary    : #e471ff;
$secondary  : #4AE4FF;
$ground : #c9ff4c;
  .footer{
     position: fixed;
    bottom:-1px;
    left: 0; 
    z-index: 99999;;
    width: 100%;

    .color{
      z-index: 99999;;
      background-color: black;
      height: 3.5rem;
      width: 100%;
      .social-link{
        @media screen and (max-width: 767px){
              display: flex;
              width: 50%;
          justify-content: space-between;
          }
        @media screen and (max-width: 1023px) and (min-width: 767px){
          display: flex;
          justify-content: center;

          left: 0%;
          width: 100%;

          a:nth-child(1){
            margin:0;
          }
        }
        display: flex;
        align-items: center;
        position: absolute;
        right: 10rem;
        bottom: 0rem;
        p{
          @media screen and (max-width: 767px){
            display: none;
          }
          padding-top: .5rem;
          color :rgba(white,0.7);
          font-size: 1.4rem;
        }
        a{
           @media screen and (max-width: 767px){
            margin: 0;
            
          }
         //
          color: white;
          font-size: 2rem;
          margin-left: 2rem;
          transition: all .3s;
          &:hover{
            color: $ground;
          }
        }
      }
    }
  }

</style>
