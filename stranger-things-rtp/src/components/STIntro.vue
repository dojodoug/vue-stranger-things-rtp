<template>
  <div class="intro">
    <div class="intro-description">
      {{ engData.description }}
    </div>
  </div>
</template>

<script>
import json from "./../data/en_US.json";
export default {
  name: "STIntro",
  data() {
    return {
      engData: json
    };
  }
};
</script>

<style>
.intro {
  flex-grow: 1;
  background-size: 100% 100%;
  background-image: url("./../assets/stranger-things-bike.jpg");
  background-repeat: no-repeat;
  padding-bottom: 18rem;
}

.intro-description {
  max-width: 35rem;
  margin: 3.25rem 0 0 1.25rem;
  padding-top: 7rem;
  color: #fff;
  text-align: left;
  font-size: 2vw;
}

@media (max-width: 980px) {
  .intro-description {
    display: grid;
    grid-template-columns: 1fr;
  }
}

@media (min-width: 760px) and (max-width: 980px) {
  .intro-description {
    display: grid;
    grid-template-columns: 0.6fr;
    margin: 0.5rem 0 0 1.25rem;
  }
}

@media (min-width: 350px) and (max-width: 760px) {
  .intro {
    padding-bottom: 7rem;
  }
  .intro-description {
    display: grid;
    grid-template-columns: 0.45fr;
    margin: 1rem 0 0 1rem;
    font-size: 0.75rem;
  }
}

@media (max-width: 350px) {
  .intro {
    padding-bottom: 2rem;
  }
  .intro-description {
    display: grid;
    grid-template-columns: 0.4fr;
    margin: 1rem 0 0 1rem;
    font-size: 0.75rem;
    padding-top: 3rem;
  }
}
</style>
