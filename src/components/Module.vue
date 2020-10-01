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
  height: 100vh;
  width: 100vw;
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  margin: 3.5rem 0;
  div {
    background-color: rgba(255, 255, 255, 0.473);
    box-shadow: 0 0 10px 0 rgb(71, 71, 71);
    padding: 20px;
    border-radius: 5px;
    height: 50%;
    width: 50%;
    backdrop-filter: blur(5px);
    margin-right: 100px;
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
