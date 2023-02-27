<template>
  <div class="header" :class="direction==='up' ? 'active' : 'hidden'">
    <div class="buttons">
      <div class="button semi-bold" @click="handleClickScroll('home')">Home</div>
      <div class="button semi-bold" @click="handleClickScroll('about-me-section')">About</div>
      <div class="button semi-bold" @click="handleClickScroll('portfolio')">Portfolio</div>
      <div class="button semi-bold" @click="handleClickScroll('skill-container')">Resume</div>
      <div class="button semi-bold" :style="{marginRight:'10px'}" @click="handleClickScroll('contact-zone')">Contact</div>
      <a href="CV.pdf" download class="button-cv semi-bold">Download CV</a>
    </div>
    <div class="button-mobile" @click=handleClickMenu :class="activeMenu ? 'active' : ''"/>
    <div class="mobile-menu" :class="activeMenu && direction==='up' ? 'active' : ''">
      <div class="button-cv semi-bold mobile" :class="{color: ''}" @click="handleClickScroll('home')">Home</div>
      <div class="button-cv semi-bold mobile" @click="handleClickScroll('about-me-section')">About</div>
      <div class="button-cv semi-bold mobile" @click="handleClickScroll('portfolio')">Portfolio</div>
      <div class="button-cv semi-bold mobile" @click="handleClickScroll('skill-container')">Resume</div>
      <div class="button-cv semi-bold mobile" @click="handleClickScroll('contact-zone')">Contact</div>
      <a href="CV.pdf" download class="button-cv semi-bold">Download CV</a>
    </div>
  </div>
</template>
<script setup>
import scrollDirection from "@/composables/scrollDirection.vue";
import {ref} from "vue";

const direction = scrollDirection();
const handleClickScroll =  (section) => {
  const element = document.getElementsByClassName(section);
  if (element) {
    element[0].scrollIntoView({ behavior: 'smooth' });
  }
  activeMenu.value = false;
};

const activeMenu = ref(false);
const handleClickMenu = () => {
  activeMenu.value = !activeMenu.value;
}
</script>
<style scoped>
@media screen and (max-width: 1250px) {
  .buttons{
    display: none !important;
  }
  .mobile-menu{
    display: flex !important;
  }
  .button-mobile{
    display: initial !important;
  }
}
.mobile-menu{
  display: none;
  position: absolute;
  background-color: #1F2235;
  top: -80px;
  right: -60px;
  transform: scale(0);
  transition: 0.3s;
  height: 250px;
  width: 200px;
  z-index: 5;
  border-radius: 10px;
  //display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  padding: 5%;
}
.mobile-menu.active{
  transform: scale(1);
  top: 80px;
  right: 15px;
}
.button-mobile{
  display: none;
  width: 50px;
  height: 50px;
  background-image: url('../assets/menu-mobile.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  cursor: pointer;
  margin-right: 10px;
  transition: 0.2s;
  z-index: 6;
}
.button-mobile.active{
  transform: rotate(90deg);
}
.header.active{
  top: 0px;
  transition: 0.5s;
}
.header.hidden{
  transition: 0.5s;
  top: -70px;
}
  .header{
    position: fixed;
    top: 0px;
    z-index: 3;
    display: flex;
    align-items: center;
    justify-content: right;
    width: 100%;
    height: 70px;
    background-color: #1F2235;
  }
  .buttons{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 30%;
    height: 100%;
    margin-right: 20px;
  }
  .button{
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    width: 50px;
    height: 15px;
    transition: 0.2s;
    cursor: pointer;

  }
  .button.mobile{
    color: #FE461C;
  }
  .button:hover{
    color: #FE461C;
  }
  .button-cv{
    width: 120px;
    height: 35px;
    color: white;
    display: flex;
    align-items:center;
    justify-content: center;
    font-size: 14px;
    background-color: #FE461C;
    border-radius: 5px;
    transition: 0.2s;
    cursor: pointer;
    text-decoration: none;

  }
  .button-cv.mobile{
    height: 25px;
  }
  .button-cv:hover{
    color: #FE461C;
    background-color: white;
  }


</style>