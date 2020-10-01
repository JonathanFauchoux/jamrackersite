<template>
  <div class="home">
    <div class="scroll-button-container">
      <button @click="scrollUp"><i class="fas fa-arrow-up"></i></button>
      <button @click="scrollDown"><i class="fas fa-arrow-down"></i></button>
    </div>
    <div class="logo_container">
      <Logo />
    </div>
    <div class="home_content">
      <h1 class="title">Titre 1</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam cum
        ducimus deleniti quos veritatis eaque ab mollitia! Ipsa laborum
        perferendis mollitia iste nam, corrupti, illo aliquid incidunt,
        accusamus dolorum rerum.Consequuntur magni quo incidunt vitae explicabo
        fugiat neque voluptatum nisi. Cumque, fuga placeat! Nihil repellendus
        quasi perferendis quo! Harum suscipit consequatur labore doloribus modi
        tempora placeat officia corrupti! Fuga, vitae!
      </p>
    </div>
    <Module :key="d.title" v-for="d in datas" :data="d" />
    <div class="footer_content">
      <h1>Music for all</h1>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Logo from "../components/Logo.vue";
import Module from "../components/Module";
import dataHome from "../dataHome.json";

export default {
  name: "Home",
  components: {
    Logo,
    Module,
  },
  data() {
    return {
      datas: dataHome,
    };
  },
  methods: {
    scrollUp() {
      window.scrollTo({
        top: window.scrollY - 1000,
        left: 0,
        behavior: "smooth",
      });
    },
    scrollDown() {
      window.scrollTo({
        top: window.scrollY + 1000,
        left: 0,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style lang="scss">
@import "../assets/main.scss";
.logo_container {
  object-fit: contain;
  height: 100vh;
  // width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.footer_content {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  h1{
    color: #159ede;
    font-size: 100px;
  }
}

.home_content {
  height: calc(100vh - 200px);
  padding: 100px 20%;
}

.scroll-button-container {
  position: fixed;
  z-index: 1000;
  bottom: 50%;
  left: 40px;
  display: flex;
  flex-direction: column;
  button {
    width: 30px;
    height: 30px;
    border: none;
    outline: none;
    border-radius: 100px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 10px 0;
    background-color: white;
    color: #159ede;
    transition: 0.2s;
    &:hover {
      background-color: rgb(241, 241, 241);
    }
  }
}

h1 {
  color: $secondary;
  margin-bottom: 20px;
}

p {
  color: black;
}
</style>
