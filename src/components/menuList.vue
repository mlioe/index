<template>
  <div class="box">
    <div class="mask" v-show="menuType">
      <div class="maskList englishType" v-for="(item,index) in menuList" :key="item" @click="maskListCLic(index)">{{item}}</div>
    </div>
      <div class="menuIcon" @click="menuClick">
        <div class="T" ref="t1"
        :style="
          currentId == 0  ? 'border: 1px solid white':'',
          currentId != 0  && menuType == false  ? 'border: 1px solid black':''
          "
        ></div>
        <div class="T" ref="t2"
        :style="
          currentId == 0  ? 'border: 1px solid white':'',
          currentId != 0  && menuType == false  ? 'border: 1px solid black':''
        "
        ></div>
        <div class="T" ref="t3"
       :style="
         currentId == 0  ? 'border: 1px solid white':'',
         currentId != 0  && menuType == false  ? 'border: 1px solid black':''
       "
        ></div>
      </div>

  </div>
</template>

<script>
export default {
  props:{
    currentId:Number
  },
  name: 'menuList',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      menuType:false,
      menuList:['Index','Catalog','Project','About']
    }
  },
  created() {
    setTimeout(()=>{
      this.$refs.t1.style.border = '1px solid white'
      this.$refs.t2.style.border = '1px solid white'
      this.$refs.t3.style.border = '1px solid white'
    },100)
  },
  methods:{
    maskListCLic(index){
      this.menuClick(index)
      this.$emit('maskList',index)
    },
    menuClick(){
      this.menuType = !this.menuType
      this.transitionMenu()
    },
    transitionMenu(){
      if(this.menuType){
        this.$refs.t2.style.opacity = '0'
        this.$refs.t1.style.transform = 'rotate(45deg) translateY(8px) translateX(7px)'
        this.$refs.t3.style.transform = 'rotate(-45deg) translateY(-8px) translateX(5px)'
      }else{
        this.$refs.t2.style.opacity = '1'
        this.$refs.t1.style.transform = 'rotate(0deg) translateY(0px) translateX(0px)'
        this.$refs.t3.style.transform = 'rotate(0deg) translateY(0px) translateX(0px)'
      }
    }
  }
}
</script>

<style scoped>
  .menuIcon{position: fixed;right: 10px;top: 3px;z-index: 3;}
  .menuIcon .T{width: 25px;margin: 8px 0px;transition: 0.5s;border: 1px solid white;}
  .mask{width: 100vw;height: 100vh;background: rgba(0,0,0,0.8);position: fixed;top: 0;z-index: 2;}
  .maskList{color: white;width: 100%;text-align: center;font-size: 24px;letter-spacing: 0.4rem;margin-bottom: 20px;}
  .maskList:nth-of-type(1){margin-top: 60px;}
</style>
