<template>
  <header id="header" class="header" :class="scrollFixed ? 'header--fixed':''">
    <div class="contHeader">
      <div class="login">
        <icon-base width="16" height="16" icon-name="lock"
          ><icon-lock />
        </icon-base>
        <span>Login</span>
      </div>
      <div class="navigation">
        <nav>
          <ul>
            <li><a class="hover" href="#">HOME</a></li>
            <li><a class="hover" href="#">ABOUT</a></li>
            <li>
              <a href="#">
                <img :src="LogoSVG"/>
              </a>
            </li>
            <li><a class="hover" href="#">JEWELS</a></li>
            <li><a class="hover" href="#">CONTACT</a></li>
          </ul>
        </nav>
      </div>
      <div class="languageSearch">
        <select name="language" class="language">
          <option value="EN">EN</option>
          <option value="ES">ES</option>
        </select>
        <icon-base width="16" height="16" icon-name="search"
          ><icon-search />
        </icon-base>
      </div>
    </div>
  </header>
</template>

<script>
import IconBase from "./IconBase";
import IconLock from "./icons/IconLock";
import IconSearch from "./icons/IconSearch";
import LogoSVG from "../assets/svg/logo.svg";
export default {
  name: "Header",
  data(){
    return{
      LogoSVG,
      scrollFixed: false
    }
  },
  components: {
    IconBase,
    IconLock,
    IconSearch
  },
  created(){
    console.log('create');
    window.addEventListener('scroll', this.handlesScroll)
  },
  destroyed () {
    console.log('destroyed');
  window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handlesScroll(){
      this.scrollFixed = window.scrollY > 100;
    }
  }
};
</script>

<style scoped>
.header{
  top: -100px;
  -webkit-transition: top 0.3s;
  transition: top 0.3s;
}
.header--fixed{
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 1;
}
.contHeader {
  height: 80px;
  background-color: #ddeaea;
  display: flex;
  align-items: center;
  padding: 0 10%;
}
.navigation a,
.navigation span {
  font-size: 1.4rem;
}
.login,
.languageSearch {
  width: 20%;
  display: flex;
  align-items: center;
}
.login svg,
.languageSearch svg {
  color: var(--color-black);
}
.login span {
  padding: 0 0 0 5px;
}
.languageSearch {
  justify-content: flex-end;
}
.navigation {
  width: 60%;
}
.navigation ul {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.navigation ul li {
  list-style-type: none;
}
.navigation ul li a {
  text-decoration: none;
  color: var(--text-color);
  position: relative;
}
.navigation ul li a.hover::after {
  content: "◆";
  color: var(--icon-color);
  text-align: center;
  width: 100%;
  display: block;
  position: absolute;
  visibility: hidden;
  opacity: 0;
  transition: visibility 0s linear 250ms, opacity 1s;
}
.navigation ul li a.hover:hover {
  font-family: "Poppins-Medium";
  color: var(--text-color-header);
}
.navigation ul li a.hover:hover::after {
  visibility: visible;
  opacity: 1;
  transition: visibility 0s linear 0s, opacity 1s;
}
.language {
  margin: 0 10px 0 0;
  border: none;
  background-color: rgb(255 255 255 / 0%);
  outline: none;
}
</style>
