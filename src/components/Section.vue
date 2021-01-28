<template>
  <section>
    <!-- <h1>section</h1> -->
  </section>
</template>

<script>
export default {
  name: "Section",
  dataCollection: [],
  data(){
    return{
      dataCollection:[
        {id: 1, name: "DIAMOSN1", description:"Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old."},
        {id: 2, name: "DIAMOSN2", description:"It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout."},
        {id: 3, name: "DIAMOSN3", description:"Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old."},
        {id: 4, name: "DIAMOSN4", description:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
        {id: 5, name: "DIAMOSN5", description:"Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but because occasionally circumstances occur in which toil and pain can procure him some great pleasure."},
        {id: 6, name: "DIAMOSN6", description:"Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old."}
      ]
    }
  }
};
</script>

<style scoped>
section {
  height: 150vh;
  /* background-color: darkslategray; */
}
</style>
