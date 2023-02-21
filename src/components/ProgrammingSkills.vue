<template>
  <div class="skill-container1">
    <div class="skill"><div class="skill-text">JavaScript</div></div>
    <div class="skill"><div class="skill-text">Git</div></div>
    <div class="skill"><div class="skill-text">Vue / React</div></div>
    <div class="skill"><div class="skill-text">REST API</div></div>
    <div class="skill"><div class="skill-text">Redux</div></div>
    <div class="skill"><div class="skill-text">HTTP / WebSocket</div></div>
    <div class="skill"><div class="skill-text">RWD</div></div>
    <div class="skill"><div class="skill-text">JWT</div></div>
  </div>
</template>

<style scoped>
.skill-container1{
  margin-top:60px;
  display:grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(3, 1fr);
  width: 70%;
  height: 200px;
}
.skill{
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  width: 240px;
  height: 50px;
  border-radius: 5px;
  background: #FE461C;
  box-shadow: 0px 0px 24px rgba(15, 16, 24, 0.42);
  transition: 0.2s;
  outline: 2px solid #FE461C;

}
.skill-text{
  font-family: 'Outfit', sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 12px;
  text-align: center;
  letter-spacing: 0.15em;
  text-transform: capitalize;
  color: white;
  cursor: context-menu;
}
.skill:hover{
  outline: 3px solid white;
}
</style>