<template>
  <div class="buttonScrollView">
    <button v-on:click='scrollView' v-show="displayButton">
      <img :src="imgSVG"/>
    </button>
  </div>
</template>

<script>
import imgSVG from '../assets/svg/arrow-in-circle-point-to-up.svg'
export default{
  name: "ScrollIntoView",
  data(){
    return{
      imgSVG,
      displayButton: false
    }
  },
  created(){
    window.addEventListener('scroll', this.handlesScroll)
  },
  destroyed () {
  window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    scrollView() {
      let elmnt = document.getElementById("main");
      elmnt.scrollIntoView({behavior: "smooth"});
    },
    handlesScroll(){
      this.displayButton = window.scrollY > 100;
    }
  }
}
</script>

<style scoped>
  .buttonScrollView{
    position: fixed;
    bottom: 160px;
    right: 50px;
  }
  .buttonScrollView button{
    background-color: rgb(255 255 255 / 0%);
    border: 0px;
    outline: none;
  }
</style>