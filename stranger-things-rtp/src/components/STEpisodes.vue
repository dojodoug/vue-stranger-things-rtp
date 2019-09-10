<template>
  <div id="episodes-div" class="episodes">
    <section class="title">
      <h1 class="title episodes-title">EPISODES</h1>
    </section>
    <section class="season1-list">
      <p>Season 1 Episodes by Rating</p>
      <ul>
        <li
          class="season1-episodes"
          v-for="episode in season1Episodes"
          v-bind:key="episode.id"
        >
            {{ episode.name }}
          <div class="rating">Rating: {{ episode.rating }}</div>
        </li>
      </ul>
    </section>
    <section class="season2-list">
      <p>Season 2 Episodes by Rating</p>
      <ul>
        <li
          class="season1-episodes"
          v-for="episode in season2Episodes"
          v-bind:key="episode.id"
        >
          {{ episode.name }}
          <div class="rating">Rating: {{ episode.rating }}</div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
import json from "./../data/en_US.json";

const episodeList = json["episode-list"];

const season1Episodes = episodeList.filter((episode) => {
  return episode.season === 1;
}).sort( (a,b) => { 
  return b.rating - a.rating
});

const season2Episodes = episodeList.filter((episode) => {
  return episode.season === 2;
}).sort( (a,b) => { 
  return b.rating - a.rating
});

export default {
  name: "STEpisodes",
  data() {
    return {
      season1Episodes: season1Episodes,
      season2Episodes: season2Episodes
    };
  }
};
</script>

<style>
.episodes {
  display: grid;
  grid-template-columns: repeat(4fr, 1fr);
  margin: 1.25rem 0;
  flex-grow: 1;
  background-size: 100%;
  background-image: url("./../assets/couch.jpg");
  background-repeat: no-repeat;
  background-position: top;
  color: #fff;
}

.title {
  text-align: left;
  font-size: 2.75vw;
  float: left;
}

.episodes-title {
  margin-left: 1.3rem;
}

.season1-list {
  grid-column: span 2;
  font-size: 2.5vw;
}

.season2-list {
  grid-column: span 2;
  font-size: 2.5vw;
}

.season1-list ul,
.season2-list ul {
  list-style-type: none;
  text-align: left;
  font-size: 1.8vw;
}

.season1-list ul {
  margin-left: 1.3rem;
}

.season2-list ul {
  padding-left: 1.7rem;
}

.season1-list li,
.season2-list li {
  margin: 10px 0px;
  color: red;
}

.rating {
  font-size: 1.5vw;
  color: #fff;
}

@media (min-width: 760px) {
  .season1-list ul {
    padding-left: 5rem;
  }

  .season2-list ul {
    padding-left: 2.75rem;
  }
}

@media (min-width: 350px) and (max-width: 760px) {
  .season1-list ul,
  .season2-list ul {
    width: 60%;
    margin: auto;
    padding-left: 1rem;
    font-size: 3.5vw;
  }
  .season1-list p,
  .season2-list p {
    font-size: 3.75vw;
  }
  .rating {
    font-size: 3vw;
  }
}

@media (max-width: 350px) {
  .title h1,
  .quote p {
    font-size: 4vw;
  }
  .season1-list ul,
  .season2-list ul {
    width: 60%;
    margin: auto;
    padding-left: 1.25rem;
    font-size: 3.5vw;
  }
  .season1-list p,
  .season2-list p {
    font-size: 3.75vw;
  }
  .rating {
    font-size: 3vw;
  }
}
</style>
