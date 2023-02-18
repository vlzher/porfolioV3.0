<template>
  <div class="header">
    <div class="buttons">
      <div class="button semi-bold">Home</div>
      <div class="button semi-bold">About</div>
      <div class="button semi-bold">Portfolio</div>
      <div class="button semi-bold">Resume</div>
      <div class="button semi-bold" :style="{marginRight:'10px'}">Contact</div>
      <div class="button-cv semi-bold">Download CV</div>
    </div>
  </div>
</template>
<style scoped>
  .header{
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
    font-size: 12px;
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
    font-size: 12px;
    background-color: #FE461C;
    border-radius: 5px;
    transition: 0.2s;
    cursor: pointer;

  }
  .button-cv:hover{
    color: #FE461C;
    background-color: white;
  }


</style>