<template>
  <main id="main">
    <Header />
    <router-view />
    <ScrollIntoView />
    <Footer />
  </main>
</template>
<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer2";
import ScrollIntoView from "./components/ScrollIntoView";
export default {
  name: "App",
  components: { Header, Footer, ScrollIntoView }
};
</script>

<style>
:root {
  --text-color: #8d8d8d;
  --text-color-header: #000000;
  --color-black: #000000;
  --color-white: #FFFFFF;
  --color-error: #e4230e;
  --color-golden: #ceb889;
  --border-color: #ceb889;
  --padding-site: 0 10%;
}
@font-face {
  font-family: "Poppins-Light";
  src: url("./assets/fonts/Poppins-Light.ttf") format("truetype");
}
@font-face {
  font-family: "Poppins-Medium";
  src: url("./assets/fonts/Poppins-Medium.ttf") format("truetype");
}
@font-face {
  font-family: "Poppins-SemiBold";
  src: url("./assets/fonts/Poppins-SemiBold.ttf") format("truetype");
}
@font-face {
  font-family: "Didot-Bold";
  src: url("./assets/fonts/Didot-Bold.ttf") format("truetype");
}
@font-face {
  font-family: "Didot-Medium";
  src: url("./assets/fonts/Didot-Medium.ttf") format("truetype");
}
@font-face {
  font-family: "Didot-Light";
  src: url("./assets/fonts/Didot-Light.ttf") format("truetype");
}
@font-face {
  font-family: "Blesing";
  src: url("./assets/fonts/Blesing.ttf") format("truetype");
}
html {
  font-size: 62.5%;
}
body {
  margin: 0px;
  box-sizing: border-box;
  color: var(--text-color);
  font-family: "Poppins-Light";
  /* background-color: #e6e6e6; */
  background-color: var(--color-white);
}
h1,
h2,
h3,
h4,
h5,
h6,
p {
  margin: 0px;
}
h1 {
  font-size: 2.5rem;
}
h2 {
  font-size: 2rem;
}
h3,
h4,
h5,
h6 {
  font-size: 1.8rem;
}
p,
a,
span {
  font-size: 1.6rem;
}
</style>
