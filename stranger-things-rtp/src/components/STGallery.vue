<template>
  <section id="gallery-div" class="gallery">
    <figure class="title gallery-title">
      <h1 class="title">GALLERY</h1> 
    </figure>
    <figure class="gallery-tiles image1">
      <img class="gallery-pics" alt="Gallery tiles" :src="galleryPics[0]" />
      <figcaption class="gallery-text">{{galleryText[0]}}</figcaption>
    </figure>
    <figure class="gallery-tiles image2">
      <img class="gallery-pics" alt="Gallery tiles" :src="galleryPics[1]" />
      <figcaption class="gallery-text">{{galleryText[1]}}</figcaption>
    </figure>
    <figure class="gallery-tiles image3">
      <img class="gallery-pics" alt="Gallery tiles" :src="galleryPics[2]" />
      <figcaption class="gallery-text">{{galleryText[2]}}</figcaption>
    </figure>
    <figure class="gallery-tiles image4">
      <img class="gallery-pics" alt="Gallery tiles" :src="galleryPics[3]" />
      <figcaption class="gallery-text">{{galleryText[3]}}</figcaption>
    </figure>
  </section>
</template>

<script>
  import json from './../data/en_US.json'

  const galleryData = json.gallery

  const galleryPics = galleryData.map((pic) => {
    return pic.src;
  })

  const galleryText = galleryData.map((pic) => {
    return pic.text;
  })

  export default {
    name: "STGallery",
    data() {
      return {
        galleryData: galleryData,
        galleryPics: galleryPics,
        galleryText: galleryText
      }
    }
  };
</script>

<style>
  .gallery {
    margin: 1.25rem;
    flex-grow: 1;
    color: #fff;
    padding-bottom: 10px;
  }

  .gallery-tiles > img {
    object-fit: cover;
    width: 100%;
    height: 90%;
    max-height: 100%;
  }

  .gallery-tiles p {
    margin-top: 5px;
  }

  @media (min-width: 760px) {
    .gallery {
      display: grid;
      grid-template-rows: 60px 400px 400px;
      grid-template-columns: repeat(2, 2fr);
      grid-gap: 20px;

      grid-template-areas: 
        "title title" 
        "img1 img2" 
        "img3 img4"; 
    }

    .gallery-title {
      grid-area: title;
    }

    .image1 {
      grid-area: img1;
      text-align: center;
    }

    .image2 {
      grid-area: img2;
      text-align: center;
    }

    .image3 {
      grid-area: img3;
      text-align: center;
    }

    .image4 {
      grid-area: img4;
      text-align: center;
    }
  }

  @media (min-width: 350px) and (max-width: 760px) {
    .gallery-tiles > img {
      object-fit: cover;
      width: 100%;
      height: auto;
      max-height: 100%;
    }
  }

  @media (max-width: 350px){
    .gallery {
      display: grid;
      grid-template-rows: 3vh 24vh 30vh 35vh 55vh;
    }
  }
</style>