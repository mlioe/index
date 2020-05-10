<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
  *{margin: 0;padding:0 ;}

  @font-face {
    font-family:'numberTypeFace';
    src: url(./assets/typeFace/HunDIN1451-1.ttf);
  }
  @font-face {
    font-family:'EnglishTypeFace';
    src: url(./assets/typeFace/Roboto-Thin-15.ttf);
  }
  @font-face {
    font-family:'chineseTypeFace';
    src: url(./assets/typeFace/Alibaba-PuHuiTi-Regular.ttf);
  }
  .numberType{font-family: "numberTypeFace";}
  .englishType{font-family: "numberTypeFace";}
  .chineseType{font-family: 'chineseTypeFace';}
#app {
/*  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
