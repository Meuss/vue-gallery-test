<template>
  <div id="app">
    <Gallery />
  </div>
</template>

<script>
import Gallery from "./components/Gallery.vue";

export default {
  name: "app",
  components: {
    Gallery
  }
};
</script>

<style>
/* @font-face {
  font-family: "Avant Garde";
  src: url("/assets/fonts/366DB7_0_0.woff2") format("woff2"),
    url("/assets/fonts/366DB7_0_0.eot") format("embedded-opentype"),
    url("/assets/fonts/366DB7_0_0.woff") format("woff"),
    url("/assets/fonts/366DB7_0_0.ttf") format("truetype");
  font-weight: 700;
  font-style: normal;
}
@font-face {
  font-family: "Avant Garde";
  src: url("/assets/fonts/366DB9_0_0.woff2") format("woff2"),
    url("/assets/fonts/366DB9_0_0.eot") format("embedded-opentype"),
    url("/assets/fonts/366DB9_0_0.woff") format("woff"),
    url("/assets/fonts/366DB9_0_0.ttf") format("truetype");
  font-weight: 400;
  font-style: normal;
} */
#app {
  font-family: "Avant Garde", "Avenir", Helvetica, Arial, sans-serif;
  text-align: center;
  background-color: #e2e2e2;
}
body {
  margin: 0px;
  padding: 30px;
  background-color: #e2e2e2;
}
@media (max-width: 768px) {
  .blueimp-gallery > .next,
  .blueimp-gallery > .prev {
    top: 90%;
  }
}
</style>
