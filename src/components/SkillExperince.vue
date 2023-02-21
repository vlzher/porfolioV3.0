<template>
  <div class="skill-container">
    <div class="skill-zone">
      <div class="text-zone">
        <div class="text-zone-text">
          Resume
        </div>
      </div>
      <div class="main-text">
        Skill & Experience
      </div>
      <div class="button-zone">
        <div class="button" :class="sectionNumber===0 ? 'active' : ''" @click="sectionNumber=0">Programming</div>
        <div class="button" :class="sectionNumber===1 ? 'active' : ''" @click="sectionNumber=1" :style="{marginLeft:'20px'}">Languages</div>
        <div class="button" :class="sectionNumber===2 ? 'active' : ''" @click="sectionNumber=2" :style="{marginLeft:'20px'}">Education</div>
      </div>
      <Transition name="custom-classes"
                  enter-active-class="animate__animated animate__backInLeft animate__faster"
                  leave-active-class="animate__animated animate__fadeOutDown animate__faster" mode="out-in" appear>
      <ProgrammingSkills v-if="sectionNumber===0"/>
      <LanguagesZone v-else-if="sectionNumber===1"/>
      <EducationZone v-else-if="sectionNumber===2"/>
      </Transition>

    </div>
    </div>
</template>
<script setup>
import ProgrammingSkills from "@/components/ProgrammingSkills.vue";
import LanguagesZone from "@/components/LanguagesZone.vue";
import {ref} from "vue";
import EducationZone from "@/components/EducationZone.vue";
import { onMounted } from "@vue/runtime-core";
import intersectionEntry from "@/composables/intersectionEntry.vue";
const sectionNumber = ref(0);
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
<style scoped>
.button-zone{
  display: flex;
  align-items: center;
  margin-top: 10px;
}
.skill-zone{
  width: 66%;
  height: 80%;
  display: flex;
  flex-direction: column;
}
.skill-container{
  width: 100vw;
  height: 90vh;
  display: flex;
  background-color: #24263B;
  justify-content: center;
  flex-direction: column;
  padding-left: 15vw;
}
.text-zone{
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

  font-family: 'Outfit', sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 48px;
  line-height: 72px;

  text-transform: capitalize;
  margin-bottom: 10px;
}
.button{
  box-shadow: 0px 0px 24px rgba(15, 16, 24, 0.42);
  width: 120px;
  height: 50px;
  color: white;
  display: flex;
  align-items:center;
  justify-content: center;
  font-size: 14px;
  background-color: #24263B;
  border-radius: 5px;
  transition: 0.2s;
  cursor: pointer;
  text-decoration: none;

}
.button:hover{
  background-color: #FE461C;
  color: white;
}
.button.active{
  background-color: #FE461C;
  color: white;
}
</style>
