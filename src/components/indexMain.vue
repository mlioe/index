<template>
  <div class="box">
      <div class="radius1">
      </div>
      <div class="by"> <span class="englishType"> BY MLIOE </span><span class="numberType">&nbsp;2017-2020</span></div>
      <div class="topRight">  </div>
      <div class="index1Main">
            <div class="numberType year">2017-2020年项目集</div>
            <div class="numberType nowYear">2020 <span class="nowYearSpan">。</span></div>
            <div class="numberType other">THIS &nbsp; IS &nbsp;MY &nbsp;PROJECT</div>
            <div class="radius2">
              <div class="radius2InRadius"></div>
            </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'indexMain',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .box{height: 100%;width: 100%;position: relative;display: flex;align-items: center;justify-content: center;}
  .radius1{width: 15px;height: 15px;border: 5px solid #fb9191 ;border-radius: 50%;position: fixed;top: 10px;left: 10px;}
  /* 介绍 */
  .by{ width: 300px;color: white;position: absolute;transform: rotate(90deg); left: -120px; bottom: 50px;border-radius: 50%;z-index: 10;}
  .index1Main{color: white;z-index: 9;position: relative;}
  .index1Main .year{font-size: 30px;}
  .index1Main .nowYear{font-size: 300px;padding: 50px 0;}
  .index1Main .nowYearSpan{font-size: 100px;}
  .index1Main .other{font-size: 20px;}
  .radius2{background-color: #FB9191;width:500px;height: 500px;position: absolute;;border-radius: 50%;z-index: -1;top: -10px;right: -180px;}
  .radius2InRadius{background-color: #fac7c7;width: 120px;height: 120px;border-radius: 50%;margin-top: 190px;margin-left: 20px;}
  /* h5 */
  @media screen and (max-width: 500px) {
     .index1Main{margin-top: -100px;}
     .index1Main .year{font-size: 20px;}
     .index1Main .nowYear{font-size: 150px;padding: 20px 0;}
     .index1Main .nowYearSpan{display: none;}
     .index1Main .other{font-size: 20px;}
  }
</style>
