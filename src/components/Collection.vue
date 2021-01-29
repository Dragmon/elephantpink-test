<template>
  <section class="collection">
    <div
    v-for='info in dataCollection'
    :key="info.id"
    class="card"
    >
      <img :src="info.img" :alt="info.name"/>
      <h3>{{ info.name }}</h3>
      <hr>
      <div class="card--Text">
        <p>{{ info.description}}</p>
      </div>
      <icon-base width="24" height="24" icon-name="lock">
        <icon-diamond />
      </icon-base>
    </div>
  </section>
</template>

<script>
import IconBase from "./IconBase";
import IconDiamond from "./icons/IconDiamond";
export default {
  name: "Collection",
  dataCollection: [],
  data(){
    return{
      dataCollection:[
        {id: 1, name: "DIAMOSN1", description:"Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC.", img:'https://images.carlosgperez.com/elephantpink/ring.jpg'},
        {id: 2, name: "DIAMOSN2", description:"It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.", img:'https://images.carlosgperez.com/elephantpink/ring.jpg'},
        {id: 3, name: "DIAMOSN3", description:"Contrary to popular belief, Lorem Ipsum is not simply random text.", img:'https://images.carlosgperez.com/elephantpink/ring.jpg'},
        {id: 4, name: "DIAMOSN4", description:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.", img:'https://images.carlosgperez.com/elephantpink/ring.jpg'},
        {id: 5, name: "DIAMOSN5", description:"Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but because occasionally circumstances.", img:'https://images.carlosgperez.com/elephantpink/ring.jpg'},
        {id: 6, name: "DIAMOSN6", description:"Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.", img:'https://images.carlosgperez.com/elephantpink/ring.jpg'}
      ]
    }
  },
  components: {
    IconBase,
    IconDiamond
  },
}
</script>

<style scoped>
.collection{
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(325px, 1fr));
  align-items: center;
  grid-gap: 15px;
  padding: var(--padding-site);
}
.card{
  border: 1px solid #000;
  min-height: 600px;
  padding: 0px 40px 30px;
  text-align: center;
}
.card h3{
  font-family: "Didot-Light";
  letter-spacing: 5px;
  color:var(--color-black);
}
.card img{
  width: 70%;
  margin: 70px 0px;
}
.card hr{
  width: 70%;
  margin: 30px auto;
}
.card--Text {
  width: 100%;
  max-height: 60px;
  text-overflow: ellipsis;
  overflow: hidden;
  margin: 0 0 30px 0;
}
.card--Text p {
  font-size: 1.3rem;
}
</style>