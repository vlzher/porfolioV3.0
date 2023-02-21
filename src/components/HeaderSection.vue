<template>
  <div class="header" :class="direction==='up' ? 'active' : 'hidden'">
    <div class="buttons">
      <div class="button semi-bold" @click="handleClickScroll('home')">Home</div>
      <div class="button semi-bold" @click="handleClickScroll('about-me-section')">About</div>
      <div class="button semi-bold" @click="handleClickScroll('portfolio')">Portfolio</div>
      <div class="button semi-bold" @click="handleClickScroll('skill-container')">Resume</div>
      <div class="button semi-bold" :style="{marginRight:'10px'}" @click="handleClickScroll('')">Contact</div>
      <a href="CV.pdf" download class="button-cv semi-bold">Download CV</a>
    </div>
  </div>
</template>
<script setup>
import scrollDirection from "@/composables/scrollDirection.vue";

const direction = scrollDirection();
const handleClickScroll =  (section) => {
  const element = document.getElementsByClassName(section);
  if (element) {
    element[0].scrollIntoView({ behavior: 'smooth' });
  }
};
</script>
<style scoped>
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
    z-index: 5;
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
  .button-cv:hover{
    color: #FE461C;
    background-color: white;
  }


</style>