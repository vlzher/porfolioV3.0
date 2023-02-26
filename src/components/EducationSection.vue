<template>
  <div class="education-zone">
    <div class="pwr-logo"></div>
    <div class="text-zone">
      <div class="text">BSc. Applied Computer Science</div>
      <div class="text">09.2022 - 03.2025</div>
    </div>
  </div>
</template>

<style scoped>
@media screen and (max-width: 1250px) {
  .pwr-logo{
    aspect-ratio: 1;
    width: 80px !important;
    height: 116px !important;
  }
  .education-zone {
    padding-left: 0 !important;

  }

}
  .education-zone{
    padding-left: 20px;
    width: 100%;
    display: flex;
    margin-top: 70px;
    align-items: center;
  }
  .pwr-logo{
    width :160px;
    height: 232px;
    background-image: url('../assets/pwr-logo.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }
  .text-zone{
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-left: 30px;
  }
  .text{
    font-size: 18px;
    color: white;
  }
</style>