<template>
  <div class="portfolio">
    <div class="portfolio-header">
      <div class="portfolio-text">
        Portfolio
      </div>
    </div>
    <div class="portfolio-container">
      <PortfolioItem :photoURL=1 fText="Crypto Price Checker" sText="Real-Time Crypto Price App" :tags="['Vue', 'LocalStorage', 'WS']" codeURL="https://github.com/vlzher/crypto-price-checker" viewURL="https://crypto-price-graph.netlify.app/"/>
      <PortfolioItem :photoURL=2 fText="Dictionary" sText="Word-Collecting App Email: test@test.com Pass: test " :tags="['React','Redux','SCSS','REST API']" codeURL="https://github.com/vlzher/dictionary-v2.0" viewURL="https://dictionary-shshshsk-vlzher.netlify.app/login"/>
      <PortfolioItem :photoURL=3 fText="Sprite NFT" :is-disabled-git=true :isDisabled=false sText="Sprite NFT APP" :tags="['React','SCSS','Ether.js']" codeURL="https://github.com/vlzher/" viewURL="https://sprite-nft.netlify.app/"/>
      <PortfolioItem :photoURL=4 fText="Kanban Board" sText="Management Tool for visualizing work" :tags="['React','Redux','Drag and Drop API']" codeURL="https://github.com/vlzher/kanban-board" viewURL="https://kanban-desk.netlify.app/"/>
      <PortfolioItem :photoURL=5 fText="Paint Analogue" sText="Simple graphic editor" :tags="['React','Canvas', 'WebSocket']" codeURL="https://github.com/vlzher/PaintAnalogue" viewURL="https://paint-analogue.netlify.app/"/>
      <PortfolioItem :photoURL=6 fText="Teamder" :isDisabled=true sText="Currently In Development" :tags="['Vue','Tailwind CSS','Vuex','JWT','REST API']" codeURL="https://github.com/vlzher/teamder"/>
    </div>
  </div>
</template>
<style scoped>
@media screen and (max-width: 1250px) {
  .portfolio-container {
    grid-template-columns: 1fr !important;
    grid-template-rows: repeat(6,1fr) !important;
  }
  .portfolio{
    height: 650vw !important;
    padding: 10% 5% 0 5% !important;
  }
  .portfolio-container{
    height: 590vw !important;
    width: 90vw !important;
    gap: 40px !important;
  }
}
.portfolio{
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 5% 5% 0 5%;
  width: 100%;
  height: 130vh;
  background-color: #1F2235;
}
.portfolio-header{
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  width: 180px;
  height: 50px;
  background: #24263B;
  box-shadow: 0px 0px 24px rgba(15, 16, 24, 0.42);
  border-radius: 4px;

}
.portfolio-text{
  font-family: 'Outfit', sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 16px;
  line-height: 12px;
  text-align: center;
  letter-spacing: 0.15em;
  text-transform: capitalize;
  color: white;
}
.portfolio-container {
  margin-top: 5vh;
  width: 60vw;
  height: 100vh;
  display: grid;
  gap: 12px;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, 1fr);
  padding: 10px;
}
</style>
<script setup>
import PortfolioItem from "@/components/PortfolioItem.vue";
import { onMounted } from "@vue/runtime-core";
import intersectionEntry from "@/composables/intersectionEntry.vue";
const { observedElement, elementClass, interOptions, interCallback, observer } =
    intersectionEntry();
onMounted(() => {
  observedElement.value = document.querySelector(".portfolio");
  elementClass.value = ["animate__animated", "animate__fadeInLeft"];
  interOptions(null, 0);
  interCallback();
  observer.observe(observedElement.value);
});
</script>