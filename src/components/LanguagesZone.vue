<template>
  <div class="language-zone">
    <div class="language">
      <div class="language-upper">
        <div class="language-text">Russian</div>
        <div class="language-text">N</div>
      </div>
      <div class="language-bar"><div :style="{width:'100%'}" class="language-progress"></div></div>
    </div>
    <div class="language">
      <div class="language-upper">
        <div class="language-text">Belarusian</div>
        <div class="language-text">N</div>
      </div>
      <div class="language-bar"><div :style="{width:'100%'}" class="language-progress"></div></div>
    </div>
    <div class="language">
      <div class="language-upper">
        <div class="language-text">Polish</div>
        <div class="language-text">B2</div>
      </div>
      <div class="language-bar"><div :style="{width:'66.66%'}" class="language-progress"></div></div>
    </div>
    <div class="language">
      <div class="language-upper">
        <div class="language-text">English</div>
        <div class="language-text">B2</div>
      </div>
      <div class="language-bar"><div :style="{width:'66.66%'}" class="language-progress"></div></div>
    </div>
    <div class="language">
      <div class="language-upper">
        <div class="language-text">Spanish</div>
        <div class="language-text">A1</div>
      </div>
      <div class="language-bar"><div :style="{width:'16.66%'}" class="language-progress"></div></div>
    </div>
  </div>
</template>

<style scoped>
  .language-zone{
    width: 70%;
    height: 80%;
    display: flex;
    flex-direction: column;
    margin-top: 40px;
  }
  .language{
    width: 100%;
    height: 70px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .language-upper{
    padding: 0 5px 0 5px;
    width: 100%;
    height: 50%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .language-text{
    font-family: 'Outfit',sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 25px;
    color: #FFFFFF;
  }
  .language-bar{
    width:100%;
    height: 30%;
    border-radius: 20px;
    background-color: #FFFFFF;
  }
  .language-progress{
    height: 100%;
    border-radius: 20px;
    background-color: #FE461C;
  }


</style>