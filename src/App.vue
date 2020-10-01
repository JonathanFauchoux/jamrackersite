<template>
  <div id="app">
    <NavBar />
    <main class="main">
      <transition name="slide" mode="out-in">
        <router-view></router-view>
      </transition>
    </main>
    <Footer />
  </div>
</template>
<script>
import NavBar from "./components/NavBar.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    NavBar,
    Footer,
  },
  data() {
    return {
      transitionName: "",
    };
  },
  mounted() {
    window.addEventListener("scroll", () => {
      if (window.scrollY > 0) {
        document.querySelector(".navbar").style.boxShadow = "0 0 10px 0 grey";
      } else {
        document.querySelector(".navbar").style.boxShadow = "none";
      }
    });
  },
  watch: {
    $route(to, from) {
      this.transitionName = to.meta.page > from.meta.page ? "next" : "prev";
    },
  },
};
</script>
<style lang="scss">
@import "./assets/main.scss";

* {
  margin: 0;
  padding: 0;
  font-family: Helvetica, sans-serif;
}
/////Scroll Bar ////
/* width */
::-webkit-scrollbar {
  width: 10px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: $primary;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #1184b9;
}

body {
  background: white;
}

html{
  overflow-x: hidden;
}
#app {
  //position: absolute;
  z-index: 0;
  color: White;
  width: 100vw;
  height: 100%;
  background-color: white;
  // overflow: hidden;
  .container {
    margin: 4rem 0 0rem 0;
    display: flex;
    justify-content: center;
    align-items: center;

    width: 100% !important;
    height: 100%;
  }
}

main {
  // width: 70vw;
  margin-inline-start: auto;
  margin-inline-end: auto;
}

/* Transition */
.slide-leave-active {
  transition: opacity 0.5s ease;
  opacity: 0;
  animation: slide-out 0.5s ease-out forwards;
}
.slide-leave {
  opacity: 1;
  transform: translateX(0);
}
.slide-enter-active {
  animation: slide-in 0.5s ease forwards;
}
@keyframes slide-out {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-30px);
  }
}
@keyframes slide-in {
  0% {
    transform: translateY(-30px);
  }
  100% {
    transform: translateY(0);
  }
}
</style>


