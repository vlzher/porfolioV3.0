<template>
  <div class="contact-zone">
    <div class="text-zone">
      <div class="text-zone-text">
        Contact
      </div>
    </div>
    <div class="main-text">
      Get In Touch
    </div>
    <div class="link-container">
      <a class="link" href="mailto:uladzhera@gmail.com"><div class="email"></div></a>
      <a class="link" href="https://github.com/vlzher"><div class="github"></div></a>
      <a class="link" href="https://www.linkedin.com/in/uladzislau-zherabiatsyeu-b90882229"><div class="linkedIn"></div></a>
    </div>
  </div>
</template>
<script setup>
  import {ref} from "vue";
  import { onMounted } from "@vue/runtime-core";
  import intersectionEntry from "@/composables/intersectionEntry.vue";
  const sectionNumber = ref(0);
  const { observedElement, elementClass, interOptions, interCallback, observer } =
  intersectionEntry();
  onMounted(() => {
  observedElement.value = document.querySelector(".contact-zone");
  elementClass.value = ["animate__animated", "animate__fadeInLeft"];
  interOptions(null, 0);
  interCallback();
  observer.observe(observedElement.value);
});
</script>
<style scoped>
@media screen and (max-width: 1250px) {
  .link-container{
    width: 90vw !important;
  }


}

.contact-zone{
  width: 100%;
  height: 50vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.text-zone{
  display: flex;
  align-items: center;
  justify-content: center;
  width: 180px;
  height: 50px;
  background: #24263B;
  box-shadow: 0px 0px 24px rgba(15, 16, 24, 0.42);
  border-radius: 4px;

}
.text-zone-text{
  font-family: 'Outfit', sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 18px;
  line-height: 12px;
  text-align: center;
  letter-spacing: 0.15em;
  text-transform: capitalize;
  color: white;
}
.main-text{
  color: #FFFFFF;
  margin-top:20px;
  font-family: 'Outfit', sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 48px;
  line-height: 72px;

  text-transform: capitalize;
  margin-bottom: 10px;
}
.link{
  width: 70px;
  height: 70px;
  background: #24263B;
  box-shadow: 0px 0px 24px rgba(15, 16, 24, 0.42);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.5s;
  outline: 1px solid #24263B;

}
.link:hover {
  transform: scale(1.1);
  outline: 1px solid #FFFFFF;
}
.link-container{
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 80%;
  height: 100px;
  margin-top: 20px;
  background-color: #24263B;
  border-radius: 1px;
}
.github{
  border-radius: 50%;
  background-repeat:no-repeat;
  background-size: cover;
  width: 35px;
  height: 35px;
  background-image: url(../assets/github.png);
}
.linkedIn {
  background-repeat:no-repeat;
  background-size: cover;
  width: 28px;
  height: 28px;
  background-image: url(../assets/linkedIn.png);
}
.email{
  background-repeat:no-repeat;
  background-size: cover;
  object-fit: cover;
  width: 26px;
  height: 19px;
  background-image: url(../assets/email.png);
}
</style>