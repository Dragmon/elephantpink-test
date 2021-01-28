<template>
  <div>
    <Slider />
    <Section />
    <Contact />
  </div>
</template>

<script>
import Section from "../components/Section";
import Slider from "../components/Slider";
import Contact from "../components/Contact";
export default {
  name: "Home",
  components: { Section, Slider, Contact }
};
</script>
