<template>
  <div class="home">
    <div class="scroll-button-container">
      <button @click="scrollUp"><i class="fas fa-arrow-up"></i></button>
    </div>
    <div class="logo_container">
      <Logo />
    </div>
    <h1>Description du projet</h1>
    <div class="home_content">
      <div data-aos="fade-down-right">
        <img
          src="https://cdn.pixabay.com/photo/2015/05/15/14/50/concert-768722_960_720.jpg"
          alt=""
        />
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
        <img
          src="https://cdn.pixabay.com/photo/2019/04/13/22/50/concert-4125832_960_720.jpg"
          alt=""
        />
        <h3>La demande du client :</h3>
        <p>
          Produire un outil musical capable de jouer des sons de différentes
          manières, de les enregistrer et de les manipuler dans un navigateur.
        </p>
      </div>
      <div data-aos="fade-up-right">
        <img
          src="https://cdn.pixabay.com/photo/2017/10/12/22/08/background-2846165_960_720.jpg"
          alt=""
        />
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
        <img
          src="https://images.pexels.com/photos/4087996/pexels-photo-4087996.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
          alt=""
        />
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
    <div class="externButton">
      <a
        class="btn --animated"
        href="https://jam-racker-orcin.vercel.app/login"
        target="_blank"
        ><span>Vous inscrire</span></a
      >
      <a
        class="btn --animated"
        href="https://jam-racker-orcin.vercel.app/login"
        target="_blank"
        ><span>Essayer JamRacker</span></a
      >
      <a class="btn --animated" href="https://github.com/Procaillass/JamRacker" target="_blank"><span>Github du projet</span></a>

      <a class="btn --animated" @click="goContact"
        ><span>Contactez nous</span></a
      >
    </div>
    <h1>Les modules</h1>
    <Module :key="d.title" v-for="d in datas" :data="d" />
    <div class="footer_content">
      <h1>Music for all</h1>
      <div id="spans">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
      </div>
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
      if (window.scrollY === 0 && this.$route.path === "/") {
        window.scrollTo({
          top: 900,
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
    goContact() {
      this.$router.push("/contact");
    },
  },
};
</script>

<style lang="scss">
@import "../assets/main.scss";

.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.externButton {
  width: 100vw;
  height: auto;
  padding: 40px 0;
  background-color: white;
  box-shadow: 0 0 10px 0 rgb(214, 214, 214);
  display: flex;
  flex-wrap: wrap;
  @media (max-width: 640px){
    flex-direction: column !important;
    margin: 0 0 40px 0;
    a{
      margin: 10px 0 !important;
    }
  }
  align-items: center;
  justify-content: center;
  margin: 100px 0;
  a {
    background-color: #159ede;
    text-decoration: none;
    margin: 0 100px;
    padding: 10px 30px;
    border: none;
    color: white;
    font-size: 16.5px;
    text-transform: uppercase;
    outline: none;
    cursor: pointer;
    &:hover {
      background-color: #1289c0;
    }
  }
}

.logo_container {
  object-fit: contain;
  height: 100vh;
  // width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  @media (max-width: 640px){
    transform: scale(0.5);
  }
}

.footer_content {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  h1 {
    color: #159ede;
    font-size: 10vw;
    position: relative;
    z-index: 100000;
    text-shadow: 0px 0px 5px rgb(255, 255, 255);
  }
}

/*Music Animation*/

.footer_content {


 #spans{
   position: absolute;
   bottom: 0;
   width: 100vw;
   height: 100%;
   display: flex;
   align-items: center;
   justify-content: center;
   z-index: 10;
 }

  span {
    opacity: 0.2;
    width: 4vw;
    height: 50vh;
    margin-left: 1px;
    background-color: #acf;
    display: inline-block;
    transform-style: preserve-3d;
    animation: music 1s infinite ease-in alternate-reverse;
  }

  span:nth-of-type(2),
  span:nth-of-type(11),
  span:nth-of-type(19) {
    animation-delay: 0.2s;
  }

  span:nth-of-type(3),
  span:nth-of-type(12),
  span:nth-of-type(20) {
    animation-delay: 0.6s;
  }

  span:nth-of-type(4),
  span:nth-of-type(13),
  span:nth-of-type(21) {
    animation-delay: 0.3s;
  }

  span:nth-of-type(5),
  span:nth-of-type(14),
  span:nth-of-type(22) {
    animation-delay: 0.7s;
  }

  span:nth-of-type(6),
  span:nth-of-type(15),
  span:nth-of-type(23) {
    animation-delay: 0.9s;
  }

  span:nth-of-type(7),
  span:nth-of-type(16),
  span:nth-of-type(24) {
    animation-delay: 1.5s;
  }

  span:nth-of-type(8),
  span:nth-of-type(17),
  span:nth-of-type(25) {
    animation-delay: 1.2s;
  }

  span:nth-of-type(9),
  span:nth-of-type(18) {
    animation-delay: 1.1s;
  }

  span:last-of-type {
    animation-delay: 1.8s;
  }

  @keyframes music {
    0% {
      height: 50px;
      background-color: #135;
    }

    25% {
      height: 75px;
      /*transform:translateZ(30px);*/
      background-color: #159ede;
    }

    50% {
      height: 100px;
      background-color: #246;
    }

    75% {
      background-color: #135;
    }
  }
}

/*End Music Animation*/

.home_content {
  // height: calc(100vh - 200px);
  width: 80vw;
  color: black;
  padding-top: 40px;
  padding-bottom: 5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  // grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  @media (max-width: 640px){
    width: 100vw;
  }

  h1 {
    color: white;
    padding: 10px;
  }

  div {
    height: 300px;
    width: 640px;
    box-shadow: 0 0 10px 0 rgb(201, 201, 201);
    @media (max-width: 640px) {
      height: 100%;
      border-radius: 0;
    }
    position: relative;
    overflow: hidden;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-end;
    img {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      object-fit: cover;
      left: 0;
      filter: brightness(0.2);
    }
    h1 {
      width: 100%;
      margin: 0;
      position: relative;
    }

    p,
    ul,
    h1,
    h3 {
      color: white;
      position: relative;
      // width: 100%;
      padding: 10px 20px 20px 20px;
      // background-color: rgba(0, 0, 0, 0.829);
    }
    p,
    li {
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
  bottom: 40px;
  right: 40px;
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
    background-color: white;
    display: none;
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
