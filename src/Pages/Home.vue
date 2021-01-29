<template>
  <div>
    <Slider />
    <Collection />
    <Contact />
  </div>
</template>

<script>
import Collection from "../components/Collection";
import Slider from "../components/Slider";
import Contact from "../components/Contact";
export default {
  name: "Home",
  components: { Collection, Slider, Contact }
};
</script>
