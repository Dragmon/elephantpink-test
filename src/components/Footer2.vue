<template>
  <footer id="footer" class="footer">
    <div class="contFooter">
      <div class="services">
        <a>Services</a>
        <span> │ </span>
        <a>Privacy and Cookie Policy</a>
      </div>
      <div class="logo">
        <img :src="LogoSVG" />
      </div>
      <div class="social-link">
        <icon-base width="20" height="20" icon-name="facebook"
          ><icon-facebook />
        </icon-base>
        <icon-base width="32" height="20" icon-name="twitter"
          ><icon-twitter />
        </icon-base>
      </div>
    </div>
    <div class="copyRight">
      <p>Copyright © 2020 DIAMONDS. All rights reserved</p>
    </div>
  </footer>
</template>

<script>
import IconBase from "./IconBase";
import IconFacebook from './icons/IconFacebook.vue';
import IconTwitter from './icons/IconTwitter.vue';
import LogoSVG from "../assets/svg/logo.svg";
export default{
  name: "Footer",
  data(){
    return{
      LogoSVG
    }
  },
  components:{
    IconFacebook,
    IconTwitter,
    IconBase
  }
}
</script>

<style scoped>
  .footer{
    min-height: 100px;
  }
  .contFooter{
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(150px, 1fr));
    align-items: center;
    padding: 30px 10%;
    background-color: var(--color-black);
    color: var(--color-white);
  }
  .contFooter .services a {
    text-decoration: underline;
    font-size: 1.5rem;
  }
  .contFooter .logo {
    justify-self: center;
  }
  .contFooter .social-link {
    justify-self: right;
  }
  .copyRight p{
    text-align: center;
  }
</style>