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
  background-position: center;
  box-shadow: 0 0 10px rgb(219, 219, 219);
  border-radius: 5px;
  @media(max-width: 640px){
    width: 100vw;
    height: 100%;
    margin: 1rem 0 0 0;
    div{
      width: 100% !important;
      margin: 0 !important;
      // height: 100% !important;
      background-color: rgba(0, 0, 0, 0.815) !important;
      *{
        color: white !important;
      }
    }
  }
  // background-repeat: no-repeat;
  // background-attachment: fixed;
  // background-position: left center;
  display: flex;
  align-items: flex-start;
  justify-content: flex-end;
  margin: 3rem 0 0rem 0;
  div {
    background-color: rgb(255, 255, 255);
    padding: 20px;
    // border-radius: 5px;
    box-shadow: 0 0 10px rgb(160, 160, 160);
    // height: 50%;
    width: 100%;
    h1 {
      position: relative;
      z-index: 10;
      color: rgb(0, 0, 0);
    }
    p {
      position: relative;
      z-index: 10;
      color:  rgb(0, 0, 0);
    }
  }
}
</style>
