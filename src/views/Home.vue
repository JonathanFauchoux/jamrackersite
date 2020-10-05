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
      <div data-aos="fade-down-right">
        <img src="https://cdn.pixabay.com/photo/2015/05/15/14/50/concert-768722_960_720.jpg" alt="">
        <h1>JamRacker</h1>
        <p>
          La musique pour tous. <br /><br />
          Projet de fin de formation professionnelle des développeurs front-end
          du Cepegra. Ce projet est une mise en situation d’une demande de
          logiciel musical par un client fictif, représenté par notre formateur
          Pierre Charlier, et produit avec notre deuxième formateur Olivier
          Belery.
        </p>
      </div>
      <div data-aos="fade-down-left">
        <img src="https://cdn.pixabay.com/photo/2019/04/13/22/50/concert-4125832_960_720.jpg" alt="">
        <h3>La demande du client :</h3>
        <p>
          Produire un outil musical capable de jouer des sons de différentes
          manières, de les enregistrer et de les manipuler dans un navigateur.
        </p>
      </div>
      <div data-aos="fade-up-right">
        <img src="https://cdn.pixabay.com/photo/2017/10/12/22/08/background-2846165_960_720.jpg" alt="">
        <h3>Conditions :</h3>
        <ul>
          <li>
            Utiliser une technologie différente pour le site de présentation et
            pour l'application.
          </li>
          <li>Avoir un lien visuel entre les deux demandes</li>
        </ul>
      </div>
      <div data-aos="fade-up-left">
        <img src="https://cdn.pixabay.com/photo/2015/10/24/09/09/studio-1004158_960_720.png" alt="">
        <h3>Technologies utilisées :</h3>
        <ul>
          <li>
            ReactJs : Composition et développement de l’application en ReactJs
            (SCSS pour l’apparence)
          </li>
          <li>VueJs : Création du site de présentation en Vue.js</li>
          <li>Firebase et Firestore pour la gestion de base de données</li>
          <li>Librairie Tone.js pour la gestion des sons.</li>
        </ul>
      </div>
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
  mounted() {
    setTimeout(() => {
      if (window.scrollY === 0) {
        window.scrollTo({
          top: 1000,
          left: 0,
          behavior: "smooth",
        });
      }
    }, 4000);
  },
  methods: {
    scrollUp() {
      window.scrollTo({
        top: 0,
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
  h1 {
    color: #159ede;
    font-size: 100px;
  }
}

.home_content {
  // height: calc(100vh - 200px);
  padding: 100px 0%;
  color: black;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  // grid-template-columns: repeat(2, 1fr);
  gap: 20px;

  h1{
    color: white;
    padding: 10px;
  }

  div{
    height: 400px;
    width: 700px;
    box-shadow: 0 0 10px 0 rgb(201, 201, 201);
    @media (max-width: 640px){
      height: 100%;
    }
    position: relative;
    overflow: hidden;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-end;
    img{
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      object-fit: cover;
      left: 0;
    }
    h1{
      width: 100%;
      margin: 0;
      position: relative;
    }
    p, ul, h1, h3{
      color: white;
      position: relative;
      // width: 100%;
      padding: 20px;
      background-color: rgba(0, 0, 0, 0.829);
    }
    p, li{
      position: relative;
      color: white;
      font-size: 20px;
    }
  }

  h3 {
    width: 100%;
    color: black;
    position: relative;
  }

  ul {
    list-style: none;
    li {
      margin: 10px 0;
    }
  }

  iframe {
    margin-top: 20px;
    width: 100%;
    height: 80%;
  }
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
