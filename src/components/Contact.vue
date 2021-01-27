<template>
  <div>
    <section id="contact" class="contact">
      <div class="contContactUs">
        <p>CONTACT US <span>Diamond</span></p>
      </div>
      <div class="contTextContact">
        <p>
          Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totoam rem aperiam, eaque ipsa quae ab illo inventore.
        </p>
      </div>
      <div class="contButton">
        <button @click="modalOpen = !modalOpen">
          CONTACT
        </button>
      </div>
    </section>
    <transition name="modal" :duration="1000">
      <div class="modal-wrapper" v-show="modalOpen" @click="leaveModal">
        <div class="modal">
          <div class="closeForm">
            <button @click="modalOpen = !modalOpen">
              CLOSE
            </button>
          </div>
          <form @submit="checkForm" >
            <div class="formInputs">
              <h1>CONTACT</h1>
              <p>Sed ut perspiciatis omnis iste natus error sit voluptatem accusantium doloremque laudantium</p>
              <input id="name" type="text" v-model="name" placeholder="Name" >
              <input id="email" type="text" v-model="email" placeholder="Email" >
              <textarea v-model="message" placeholder="Your message here" ></textarea>
              <div class="messageForm">
                <H3 v-if="errors.length">Error</H3>
                <ul>
                  <li v-for="error in errors" :key="error">{{ error }}</li>
                </ul>
              </div>
            </div>
            <div class="formButton">
              <input type="submit" value="SEND">
            </div>
          </form>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data(){
    return{
      modalOpen: false,
      message:'',
      name: '',
      email: '',
      errors:[]
    }
  },
  methods:{
    leaveModal({currentTarget, target}){
      console.log('currentTarget', currentTarget);
      console.log('target', target);
      if (currentTarget === target) {
        this.modalOpen = !this.modalOpen
      }
    },
    checkForm: function(e){
      this.errors=[]
      if (this.name && this.email && this.message) {
        this.errors.push("Unexpected server error")
      }
      if (!this.name) {
        this.errors.push("Name required")
      }
      if (!this.email) {
        this.errors.push("Email required")
      }
      if (!this.message) {
        this.errors.push("Message required")
      }
      e.preventDefault();
    }
  }
}
</script>

<style scoped>
.contact{
  display: flex;
  flex-direction: row;
  align-items: center;
  margin: 0 10%;
  padding: 25px 30px;
  background-color: #FFFFFF;
}
.contContactUs {
  width: 20%;
}
.contContactUs p {
  font-size: 2rem;
  font-family: 'Poppins-SemiBold';
  color:var(--color-golden);
}
.contContactUs p span {
  font-family: 'Blesing';
  color: var(--color-black);
}
.contTextContact {
  width: 65%;
  padding: 0 25px 0 35px;
}
.contButton {
  width: 15%;
}
.contButton button {
  width: 100%;
  height: 40px;
  background-color: var(--color-width);
  border: 1px solid var(--color-black);
}
.modal-wrapper {
  position: fixed;
  border-radius: 4px;
  background: rgba(0, 0, 0, 0.4);
  width: 100vw;
  height: 100vh;
  top: 0;
  left: 0;
  overflow-y: scroll;
}
.modal {
  padding: 20px;
  max-width: 500px;
  margin: 120px auto;
  z-index: 10;
}
.closeForm button{
  border: none;
  background-color: rgba(255, 255, 255, 0);
  color: var(--color-white);
  padding: 20px 0;
  font-size: 1.5rem;
  outline: none;
}
.formInputs{
  background-color: var(--color-white);
  padding: 60px 35px;
  text-align: center;
  color: var(--color-black);
}
.formInputs h1,
.formInputs p {
  margin: 0 0 30px;
}
.formInputs h1{
  font-family: "Didot-Bold";
  font-size: 3rem;
  letter-spacing: 5px;
}
.formInputs p{
  font-size: 1.2rem;
}
.formInputs input{
  width: 100%;
  margin: 0 0 10px;
  box-sizing: border-box;
  padding: 10px;
  font-size: 1.6rem;
  border: 1px solid #cbcbcb;
  outline: none;
}
.formInputs textarea{
  width: 100%;
  height: 150px;
  box-sizing: border-box;
  padding: 10px;
  font-size: 2.3rem;
  border: 1px solid #cbcbcb;
  outline: none;
}
.formInputs input:focus,
.formInputs textarea:focus{
  border: 2px solid var(--border-color);
}
.formButton input{
  width: 60%;
  margin: 20px 20% 0;
  padding: 20px 0;
  background-color: var(--color-golden);
  border: none;
}
.messageForm{
  color: var(--color-error);
  margin: 20px 0 0;
}
.messageForm ul{
  list-style: none;
  padding: 0;
  font-size: 1.3rem;
  font-style: italic;
}

/* Using the class hook to animate some intern element */

.modal-enter-to .modal {
  animation: slide 1s;
}

.modal-leave-to .modal {
  animation: slide 1s reverse;
}

.modal-enter,
.modal-leave-to {
  opacity: 0;
}

.modal-enter-active,
.modal-leave-active {
  transition: all 0.3s;
}

@keyframes slide {
  from {
    transform: translate3d(0, -40px, 0);
  }
  to {
    transform: translate3d(0, 0px, 0);
  }
}
</style>