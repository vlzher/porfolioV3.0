<template>
  <div
    class="project"
    @mouseleave="(e) => mouseLeaveProject(e)"
    @mouseenter="(e) => mouseEnterProject(e)"
  >
    <div class="project-head">
      <img :src="imagePath" alt="" class="img-fluid card-img custom-img" />
      <div class="project-overlay" style="top: 0">
        <h4>{{ fText }}</h4>
      </div>
      <div class="project-hover" style="top: 100%">
        <div class="project-body text-center">
          <h3 class="title">{{ sText }}</h3>

          <ul
            class="filters filters-tag text-center"
            :style="{ marginTop: '10px' }"
            @click="(e) => filterClick(e)"
          >
            tech:
            <li :style="{ marginTop: '5px' }" v-for="tag in tags">
              <a>{{ tag }}</a>
            </li>
          </ul>

          <div class="btn-group" role="group">
            <a
              :href="codeURL"
              :class="isDisabledGit ? 'disabled': ''"
              class="btn project-btn"
              ><i class="fas fa-code"></i> Code</a
            >
            <a
              :href="viewURL"
              :class="isDisabled ? 'disabled' : ''"
              class="btn project-btn"
              ><i class="far fa-eye"></i> View</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { computed, ref } from "vue";

const isActive = ref(false);

const props = defineProps({
  photoURL: Number,
  fText: String,
  sText: String,
  tags: Array[String],
  codeURL: String,
  viewURL: String,
  isDisabled: Boolean,
  isDisabledGit: {
    type: Boolean,
    default: false,
  },
});
const imagePath = computed(() => {
  switch (props.photoURL) {
    case 1:
      return new URL("../assets/coin-price-checker.png", import.meta.url);
    case 2:
      return new URL("../assets/dictionary.png", import.meta.url);
    case 3:
      return new URL("../assets/sprite.png", import.meta.url);
    case 4:
      return new URL("../assets/kanban-board.png", import.meta.url);
    case 5:
      return new URL("../assets/paintAnalogue_475x232.png", import.meta.url);
    case 6:
      return new URL("../assets/teamder.png", import.meta.url);
  }
});
const filterClick = (e) => {
  e.preventDefault();
  isActive.value = !isActive.value;
};
const mouseEnterProject = (e) => {
  e.preventDefault();
  const projectOverlay = e.target.querySelector(".project-overlay");
  const projectHover = e.target.querySelector(".project-hover");
  projectOverlay.style.top = "-100%";
  projectHover.style.top = "0px";
};
const mouseLeaveProject = (e) => {
  e.preventDefault();
  const projectOverlay = e.target.querySelector(".project-overlay");
  const projectHover = e.target.querySelector(".project-hover");
  projectOverlay.style.top = "0px";
  projectHover.style.top = "100%";
};
</script>

<style scoped>
@media screen and (max-width: 1250px) {
  .project:nth-child(2) {
    grid-row: 2 / 3 !important;
    grid-column: 1 !important;
  }
  .project:nth-child(4) {
    grid-row: 4 / 5 !important;
    grid-column: 1 !important;
  }
  .project:nth-child(6) {
    grid-row: 6 / 7 !important;
    grid-column: 1 !important;
  }
}
.custom-img {
  border: none;
  border-radius: 15px;
  outline: 2px solid #24263b;
  background-size: cover;
  background-position: center;
  width: 100%;
  height: 100%;
  aspect-ratio: 1;
}
ul.filters {
  display: block;
  width: 100%;
  margin: 0;
  padding: 30px 0;
}

ul.filters > li {
  list-style: none;
  display: inline-block;
}

ul.filters > li > a {
  display: block;
  color: #434e5e;
  text-decoration: none;
  padding: 5px 20px;
}

ul.filters > li > a:hover {
  background-color: #e6e9ed;
}

ul.filters > li.active > a {
  color: #fff;
  background-color: rgba(254, 70, 28, 1);
}

.filters.filters-tag {
  display: inline-block;
  padding: 0.25em 0.4em;
  font-size: 75%;
  line-height: 1;
  text-align: center;
}

ul.filters.filters-tag > li > a {
  display: block;
  color: #ffffff;
  border-radius: 0.25rem;
  padding: 0.3rem 0.6rem;
}

ul.filters.filters-tag > li > a:hover {
  color: #fff;
  background-color: rgba(254, 70, 28, 1);
  transition: 0.1s;
}

.filters-tag {
  font-size: 0.9rem;
}

.project {
  outline: 2px solid #24263b;
  border-radius: 20px;
  grid-column: span 1;
  background-color: rgba(255, 255, 255, 0.8);
  font-size: 30px;
  text-align: center;
}
.project:nth-child(2) {
  grid-row: 1 / 3;
  grid-column: 2;
}
.project:nth-child(4) {
  grid-row: 2 / 4;
  grid-column: 1;
}
.project:nth-child(6) {
  grid-row: 2 / 4;
  grid-column: 3;
}

.project-head {
  position: relative;
  overflow: hidden;
  width: 100%;
  height: 100%;
  border-radius: 10px;
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 9;
  background-color: rgba(36, 38, 59, 0.8);
  display: flex;
  padding-top: 45%;
  justify-content: center;
  color: #ffff;
  -webkit-transition: ease-in-out 0.2s;
  -moz-transition: ease-in-out 0.2s;
  -ms-transition: ease-in-out 0.2s;
  transition: ease-in-out 0.2s;
}

.project-hover {
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(254, 70, 29, 0.9);
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  flex-direction: column;
  box-sizing: border-box;
  padding: 30px;
  -webkit-transition: ease-in-out 0.2s;
  -moz-transition: ease-in-out 0.2s;
  -ms-transition: ease-in-out 0.2s;
  transition: ease-in-out 0.2s;
}

.project-body {
  padding-top: 10px;
  padding-bottom: 10px;
}

h3.title {
  color: #ffffff;
  font-size: 1.75rem;
  margin-bottom: 0;
  white-space: pre-line;
}

.project-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 10px -40px 10px;
  font-size: 0.9rem;
  background-color: #fff;
  color: #222;
  border: 1px solid #eee;
  border-radius: 0;
  width: 120px;
  box-shadow: 1px 1px 1.5px rgba(0, 0, 0, 0.075);
}

.project-btn:hover {
  background-color: rgba(254, 70, 28, 1);
  color: #ffffff;
}
</style>
