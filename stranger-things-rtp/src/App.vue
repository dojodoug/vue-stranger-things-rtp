<template>
  <div id="app">
    <STHeader></STHeader>
    <STIntro></STIntro>
    <STInspiration></STInspiration>
    <STGallery></STGallery>
    <STEpisodes></STEpisodes>
  </div>
</template>

<script>
  import STHeader from "./components/STHeader.vue";
  import STIntro from "./components/STIntro.vue";
  import STInspiration from "./components/STInspiration.vue";
  import STGallery from "./components/STGallery.vue";
  import STEpisodes from "./components/STEpisodes.vue";

  export default {
    name: "app",
    components: {
      STHeader,
      STIntro,
      STInspiration,
      STGallery,
      STEpisodes
    }
  };
</script>

<style>
  #app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    height: 100%;
    width: 100%;
  }

  html{
    background-color: #000;
  }

  body {
    font-family: 'ITC Benguiat', sans-serif;
    min-width: 350px;
    margin: 0;
    height: 100%;
    margin: 0;
    padding: 0;
  }
</style>
