<template>
  <div class="box">
      <div class="list chineseType">
        <div class="title">
          TECHNOLOGY
          <div class="before"></div>
        </div>
        <div class="text"><span>VUE </span> <span>REACT(半桶水)</span></div>
      </div>
      <div class="list chineseType">
        <div class="title">
          FRAME
            <div class="before"></div>
        </div>
        <div class="text"><span>UNI—APP</span> <span>ELEMENT-UI</span> <span>ANT DESGIN</span> </div>
      </div>
      <div class="list chineseType">
        <div class="title">
          H5
           <div class="before"></div>
        </div>
        <div class="text"><span>杏林春雨服务号H5</span></div>
      </div>
      <div class="list chineseType">
        <div class="title">
         APP
         <div class="before"></div>
        </div>
        <div class="text"><span>杏林春雨医生问诊端(UNI-APP开发)</span> <span>腾龙易聘(UNI-APP开发)</span></div>
      </div>
      <div class="list chineseType">
        <div class="title">APPLET
          <div class="before"></div>
        </div>
        <div class="text"><span>杏林春雨医生问诊端(UNI-APP开发)</span> <span>腾龙易聘(UNI-APP开发)</span> </div>
      </div>
      <div class="raduis1"></div>
      <div class="raduis2"></div>
      <div class="raduis3"></div>
  </div>
</template>

<script>
export default {
  name: 'indexMain',
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .box{width: 100;height: 100vh;display: flex;justify-content: center;flex-direction: column;position: relative;}
  .list{margin-left: 100px;z-index: 9;}
  .list .title{color: #ff3737;font-size: 40px;font-weight: bold;position: relative;padding-left: 20px;}
  .list .title .before{width: 10px;height: 10px;border: 6px solid #FF4D4D;position: absolute;left: -5px;bottom: 15px;border-radius: 50%;}
  .list .text{font-size: 16px;margin: 20px 0;}
  .list .text span{margin-right: 30px;color: #808080;}

  @media screen and (max-width: 500px) {
     .box{}
     .before{display: none;}
     .list{margin: 0;}
     .list .title{font-size: 28px;padding-left: 20px;width: 100%;color: black;}
     .list .text{font-size: 16px;margin:20px 0;width: 100%;align-items: center;justify-content: space-between;flex-wrap: wrap;margin-left: 20px;box-sizing: border-box;padding-right: 20px;}
       .raduis1{background-color: #f2f7fd;width: 150px;height: 150px;position: absolute;top: 50%;z-index: 1;border-radius: 150px;margin-top: -75px;left: 30px;}
       .raduis2{width: 150px;height: 150px;position: absolute;top: 50%;z-index: 1;border-radius: 150px;margin-top: -75px;left: 105px;border: 20px solid #F2F7FD;box-sizing: border-box;}
  }


</style>
