<template>
  <div>
    <carousel
    :navigationEnabled="true"
    :perPage="1"
    :loop="true"
    navigationNextLabel=""
    navigationPrevLabel=""
    paginationActiveColor=var(--color-golden)
    >
      <slide
      v-for='data in dataSlider'
      :key="data.id"
      :style="{backgroundImage:`url(${data.img})`}"
      >
        <div class="infoSlide">
          <h3>{{ data.title }}</h3>
          <hr>
          <p>{{ data.info}}</p>
        </div>
      </slide>
    </carousel>
  </div>
</template>

<script>
import { Carousel, Slide } from 'vue-carousel';
export default {
  name: "Slider",
  dataSlider:[],
  data(){
    return{
      dataSlider:[
        {id: 1, title: 'DIAMONDS', img:'https://images.carlosgperez.com/elephantpink/background-diamonds.jpg', info: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.'},
        {id: 2, title: 'GOLD', img:'https://images.carlosgperez.com/elephantpink/background-diamonds2-min.png', info: 'The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested.'},
        {id: 3, title: 'SILVER', img:'https://images.carlosgperez.com/elephantpink/background-diamonds.jpg', info: 'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.'},
      ]
    }
  },
  components:{
    Carousel,
    Slide
  }
}
</script>

<style>
.VueCarousel-slide {
  position: relative;
  background: #68756f;
  color: #fff;
  font-family: Arial;
  font-size: 24px;
  text-align: center;
  min-height: 70vh;
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
}
.VueCarousel-slide::before {
	content:'';
	position: absolute;
  top: 0;
	bottom: 0;
	left: 0;
	right: 0;
	background-color: rgba(0,0,0,0.6);
}
.infoSlide {
  min-height: inherit;
  max-width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  position: relative;
}
.infoSlide hr {
  width: 35%;
}
.VueCarousel-navigation-prev {
  margin: 0 0 0 10% !important;
  transform: none;
  height: 25px;
  width: 25px;
}
.VueCarousel-navigation-prev::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: inherit;
  width: inherit;
  background-image: url('../assets/svg/arrow-left.svg');
  background-repeat: no-repeat;
}
.VueCarousel-navigation-next {
  margin: 0 10% 0 0 !important;
  height: 25px;
  width: 25px;
}
.VueCarousel-navigation-next::before {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  height: inherit;
  width: inherit;
  background-image: url('../assets/svg/arrow-right.svg');
  background-repeat: no-repeat;
}
.VueCarousel-pagination {
  position: absolute;
  bottom: 20px;
}
.VueCarousel-navigation-next,
.VueCarousel-navigation-prev,
.VueCarousel-pagination button{
  outline: none !important;
}

</style>