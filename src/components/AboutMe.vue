<template>
  <div class="about-me-section">
    <div class="about-me-section1">
      <div class="photo"></div>
      <div class="about-me">
        <div class="about-me-content">
          <div class="about-me-header">
            <div class="about-me-header-text">About Me</div>
          </div>
          <div class="about-me-content-header">Uladzislau Zherabiatsyeu</div>
          <div class="about-me-content-text">
            I am a 2-year computer science student with a passion for programming.
            I have experience in multiple programming languages and am always looking to learn more.
            I am a strong communicator and enjoy working on projects that allow me to collaborate with others.
            I am excited to continue honing my skills and building a diverse portfolio of work in the tech industry.
          </div>
          <div class="button-section">
            <a href="CV.pdf" download class="button-cv semi-bold">Download CV</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { onMounted } from "@vue/runtime-core";
import intersectionEntry from "@/composables/intersectionEntry.vue";
const { observedElement, elementClass, interOptions, interCallback, observer } =
    intersectionEntry();
onMounted(() => {
  observedElement.value = document.querySelector(".about-me-section1");
  elementClass.value = ["animate__animated", "animate__fadeInLeft"];
  interOptions(null, 0);
  interCallback();
  observer.observe(observedElement.value);
});
</script>

<style scoped>
  .about-me-section{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 120vh;
    background-color: #24263B;
  }
  .about-me-section1{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 120vh;

    padding: 2.5% 5% 5% 5%;
  }
  .photo{
    width: 60vh;

    aspect-ratio: 1;
    background-image: url('/src/assets/about-me-photo.png');
    background-size: cover;
    background-position: center;
  }
  .about-me{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    width: 600px;
    height: 100%;
    margin-left: 10vw;
    margin-right: 50px;
  }
  .about-me-header{
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
    width: 130px;
    height: 50px;
    background: #24263B;
    box-shadow: 0px 0px 24px rgba(15, 16, 24, 0.42);
    border-radius: 4px;

  }
  .about-me-header-text{
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
  .about-me-content{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    width: 100%;
    height: 100%;
    margin-bottom: 10px;
  }
  .about-me-content-header{
    font-family: 'Outfit',sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 45px;
    line-height: 48px;
    color: #FFFFFF;
    margin-bottom: 20px;
  }
  .about-me-content-text{
    width: 612px;
    height: 130px;
    font-family: 'Public Sans', sans-serif;
    font-style: normal;
    font-weight: 300;
    font-size: 16px;
    line-height: 26px;
    color: #FFFFFF;
    margin-bottom: 10px;
  }
  .button-section {
    display: flex;
    align-items: center;
    justify-content: right;
    width: 100%;
    height: 50px;
  }
  .button-cv{
    width: 120px;
    height: 50px;
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