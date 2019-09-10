<template>
  <div id="inspiration-div" class="inspiration">
    <section class="title">
      <img
        class="st-logo"
        alt="Stranger Things logo"
        src="./../assets/stranger-things_raw.png"
      />
      <h1 class="title inspiration-title">INSPIRATION</h1>
    </section>
    <section class="quote">
      <p>"{{ engData.quote.text }}"</p>
      <p>- {{ engData.quote.author }}</p>
    </section>
    <section class="inspiration-text">
      <ul>
        <li
          class="snippets"
          v-for="snippet in snippetData"
          v-bind:key="snippet.id"
        >
          {{ snippet }}
        </li>
        <li
          class="locations"
          v-for="location in locations"
          v-bind:key="location.id"
        >
          {{ location }}
        </li>
      </ul>
    </section>
    <section class="video-container st-video">
      <iframe
        class="video-iframe"
        alt="Stranger Things video"
        :src="engData['video-embed']"
        allow="encrypted-media"
        allowfullscreen
      ></iframe>
    </section>
  </div>
</template>

<script>
import json from "./../data/en_US.json";
export default {
  name: "STInspiration",
  data() {
    return {
      engData: json,
      snippetData: json.snippets,
      locations: json.locations
    };
  }
};
</script>

<style>
.inspiraton-div {
  scroll-padding-top: 20px;
}
.inspiration {
  display: grid;
  grid-template-columns: repeat(10fr, 1fr minmax(300px, 1fr));
  height: 100%;
  margin: 1.25rem;
  color: #fff;
}

.title {
  text-align: left;
  font-size: 2.75vw;
  float: left;
}

.inspiration-title {
  margin-right: 3rem;
}

.st-logo {
  float: left;
  width: 100%;
  max-width: 350px;
  height: auto;
  object-fit: cover;
}

.quote p {
  margin-top: 0;
  font-size: 2.25vw;
}

.inspiration-text ul {
  text-align: left;
  padding-left: 0;
  font-size: 1.25vw;
  margin: 0;
  margin-right: 15px;
}

.inspiration-text li {
  margin-bottom: 8px;
}

.snippets {
  list-style-type: none;
}

.locations {
  margin-left: 1rem;
}

.video-container {
  position: relative;
  overflow: hidden;
  padding-top: 56.25%;
}

.video-iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}

@media (min-width: 760px) {
  .inspiration {
    display: grid;
    grid-template-columns: repeat(10, 1fr);
  }

  .title {
    grid-column: span 5;
    grid-row: span 1;
  }

  .quote {
    grid-column: span 5;
    grid-row: span 1;
  }

  .inspiration-text {
    grid-column: span 5;
    grid-row: span 2;
  }

  .st-video {
    grid-column: span 5;
    grid-row: span 1;
  }
}

@media (min-width: 350px) and (max-width: 760px) {
  .title {
    display: grid;
  }
  .title h1,
  .quote p {
    font-size: 3vw;
  }
  .inspiration-text ul {
    font-size: 2.5vw;
  }
}

@media (max-width: 350px) {
  .title h1,
  .quote p {
    font-size: 4vw;
  }
  .inspiration-text ul {
    font-size: 2.5vw;
  }
}
</style>
