<template>
  <header class="header-container">
    <div class="header">
      <STNav></STNav>
      <p class="header-text">{{ engData.heading }}</p>
    </div>
  </header>
</template>

<script>
import STNav from "./STNav.vue";
import json from "./../data/en_US.json";
export default {
  name: "STHeader",
  data() {
    return {
      engData: json
    };
  },
  components: {
    STNav
  }
};
</script>

<style>
.header-container {
  padding-bottom: 10px;
}
.header {
  position: fixed;
  width: 100%;
  background-color: #000;
}

.header-text {
  text-align: left;
  color: red;
  padding: 0.5rem 1.5rem;
  margin-left: 3rem;
  margin-top: 0;
  margin-bottom: 0;
}

.spacer {
  width: 95%;
  height: 95px;
}

@media (min-width: 980px) {
  .header {
    font-size: 3vw;
  }
}

@media (min-width: 760px) and (max-width: 980px) {
  .header {
    font-size: 3vw;
    padding-bottom: 15px;
  }
}

@media (min-width: 350px) and (max-width: 760px) {
  .header {
    font-size: 5vw;
    padding-bottom: 15px;
  }
}

@media (max-width: 350px) {
  .header {
    font-size: 6vw;
    padding-bottom: 15px;
  }
}
</style>
