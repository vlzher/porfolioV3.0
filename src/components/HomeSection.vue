<template>
  <div class="home">
    <div class="home-content">
      <div class="home-header">Welcome my portfolio</div>
      <div class="home-main-text">Hey, I'm Uladzislau <span class="text-span" :style="{color: '#FE461C'}">Front-End</span> Developer.</div>
      <div class="home-sub-text">Web development is not just about creating pretty websites.
        It's about understanding the world we live in and creating solutions
        that make people's lives easier.</div>
    </div>
    <div class="photo"></div>
  </div>
</template>

<style scoped>
@media screen and (max-width: 1250px) {
  .home{
    flex-direction: column-reverse;
    height: 80vh !important;
    justify-content: flex-end !important;
    padding-top: 80px !important;
    padding-left: 0 !important;
    padding-right: 0 !important;
  }
  .photo{

    height: 250px !important;
    width: 250px !important;
    margin-left: 0 !important;
  }
  .home-content{
    margin: 30px 0 0 0 !important;
    width: 85% !important;
    height: 300px !important;
  }
  .home-main-text{
    line-height: initial !important;
    height: auto !important;
  }
  .home-sub-text{
    width: 100% !important;
    text-align: center;
    height: auto !important;
  }

}
  .home{
    display: flex;
    justify-content:  center;
    align-items: center;
    width: 100%;
    height: calc(100vh + 70px);
    padding: 0 5% 100px 5%;
    background-color: #1F2235;
  }
  .home-content{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    width: 50%;
    height: 100%;
    margin-left: 20px;
  }
  .home-header{
    font-family: 'Public Sans', sans-serif;;
    font-style: normal;
    font-weight: 900;
    font-size: min(16px,4cqi);
    line-height: 20px;

    letter-spacing: 0.15em;
    text-transform: capitalize;

    color: #FFFFFF;
    margin-bottom: 10px;
  }
  .home-main-text{
    width: min(80vw, 654px);
    height: 131px;
    left: 300px;
    top: 367px;
    color: #FFFFFF;

    font-family: 'Outfit', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: min(8cqi,64px);
    line-height: 72px;

    text-transform: capitalize;
    margin-bottom: 10px;
  }
  .home-sub-text{
    width: 501px;
    height: 90px;
    font-family: 'Public Sans', sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: min(15px,3.5cqi);

    line-height: 30px;
    color: #FFFFFF;
    margin-bottom: 10px;
    margin-top: 10px;
  }
  .photo{
    margin-left: 50px;
    width:  500px;
    aspect-ratio: 1;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
    border-radius: 500px;
    background-image: url('/src/assets/logo-home.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;


  }
</style>