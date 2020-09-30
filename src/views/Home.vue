<template>
  <div class="home">
    <div class="logo_container">
      <Logo/>
    </div>
    <h1 class="title">Titre 1</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam cum
      ducimus deleniti quos veritatis eaque ab mollitia! Ipsa laborum
      perferendis mollitia iste nam, corrupti, illo aliquid incidunt, accusamus
      dolorum rerum.Consequuntur magni quo incidunt vitae explicabo fugiat neque
      voluptatum nisi. Cumque, fuga placeat! Nihil repellendus quasi perferendis
      quo! Harum suscipit consequatur labore doloribus modi tempora placeat
      officia corrupti! Fuga, vitae!
    </p>
    <Module/>
  </div>
</template>

<script>
// @ is an alias to /src
import Logo from '../components/Logo.vue'
import Module from '../components/Module'

export default {
  name: "Home",
  components: {
    Logo,
    Module
  },
};
</script>

<style lang="scss">

.logo_container{
  object-fit: contain;
  height: 100vh;
  // width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}


h1 {
  color: black;
  margin-bottom: 20px;
}

p{
  color:black;
}
</style>
