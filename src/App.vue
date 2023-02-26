<template>
  <HeaderSection/>
  <div class="ellipse"></div>
  <Transition name="custom-classes"
              enter-active-class="animate__animated animate__zoomInDown"
              appear>
  <HomeSection/>
  </Transition>
  <AboutMe />
  <PortfolioSection/>
  <SkillExperince/>
  <ContactSection/>
  <FooterSection/>
</template>
<script setup>

import HeaderSection from "@/components/HeaderSection.vue";
import HomeSection from "@/components/HomeSection.vue";
import AboutMe from "@/components/AboutMe.vue";
import PortfolioSection from "@/components/PortfolioSection.vue";
import SkillExperince from "@/components/SkillExperince.vue";
import ContactSection from "@/components/ContactSection.vue";
import FooterSection from "@/components/FooterSection.vue";
</script>
<style scoped>
.ellipse{
  position: absolute;
  width: 204px;
  height: 204px;
  left: 120px;
  top: 150px;
  border-radius: 50%;
  background: rgba(187, 197, 211, 0.08);
  z-index: 5;
}
</style>
