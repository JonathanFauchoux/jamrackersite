<template>
  <div data-aos="zoom-in" v-bind:style="{backgroundImage: 'url(' + data.image + ')' }" class="module">
    <div data-aos-delay='300' data-aos="fade-left">
      <h1>{{data.title}}</h1>
      <p>
        {{data.description}}
      </p>
    </div>
  </div>
</template>


<script>
export default {
  name: "Module",
  components: {},
  props: ["data"],
};
</script>
<style lang="scss">
.module {
  overflow: hidden;
  height: 70vh;
  width: 80vw;
  position: relative;
  background-size: cover;
  @media(max-width: 640px){
    width: 100vw;
    margin: 1rem 0 0 0;
  }
  // background-repeat: no-repeat;
  // background-attachment: fixed;
  // background-position: left center;
  display: flex;
  align-items: flex-start;
  justify-content: flex-end;
  margin: 3rem 0 0rem 0;
  div {
    background-color: rgba(0, 0, 0, 0.473);
    box-shadow: 0 0 10px 0 rgb(20, 20, 20);
    padding: 20px;
    border-radius: 5px;
    // height: 50%;
    width: 50%;
    backdrop-filter: blur(5px);
    margin-right: 40px;
    margin-top: 40px;
    h1 {
      position: relative;
      z-index: 10;
      color: rgb(255, 255, 255);
    }
    p {
      position: relative;
      z-index: 10;
      color:  rgb(255, 255, 255);
    }
  }
}
</style>
