<template>
  <Slide>
    <a id="inspiration" href="#inspiration-div" v-scroll-to="'#inspiration-div'">
      <span>INSPIRATION</span>
    </a>
    <a id="gallery" href="#gallery-div">
      <span>GALLERY</span>
    </a>
    <a id="episodes" href="#episodes-div">
      <span>EPISODES</span>
    </a>
  </Slide>
</template>

<script>
  import { Slide } from 'vue-burger-menu'
  export default {
    name: "STNav",
    components: {
      Slide
    }
  };
</script>

<style>
  .bm-burger-button {
    top: 15px;
    left: 20px;
  }

  .bm-burger-bars {
    background-color: #fff;
  }
</style>