<template>
  <div class="box">
    <v-touch v-on:swipeleft="swiperleft" v-on:swiperight="swiperright" v-on:swipeup="swipeup" v-on:swipedown="swipedown" class="wrapper">
    <div class="mainBox" ref="addAlert">
      <div class="main">
       <main1></main1>
      </div>
      <div class="main">
        <main2></main2>
      </div>
      <div class="main" style="display: flex;align-items: center;justify-content: center;">在做了做了，咕咕咕咕</div>
      <div class="main" style="display: flex;align-items: center;justify-content: center;">在做了做了，咕咕咕咕</div>
    </div>
    </v-touch>
    <div class="pages numberType" :style="currentId == 0 ? 'color:white':''">page {{currentId+1}}</div>
    <div class="menu"  :style="currentId == 0 ? 'color:white':''">
      <div class="menuList englishType" v-for="(item,index) in menuList" :key="item" @click="menCLick(index)">{{item}}</div>
    </div>
    <div class="h5Menu">
      <menu-list @maskList="maskList" :currentId="currentId"></menu-list>
    </div>
  </div>
</template>

<script>
  import main1 from '../../components/indexMain.vue'
  import main2 from '../../components/indexMain2.vue'
  import menuList from '../../components/menuList.vue'
  export default {
    components: {
     main1,main2,menuList
    },
    data() {
      return {
        currentId: 0,
        menuList:['Index','Catalog','Project','About']
      }
    },
    created(){
      setTimeout(()=>{
        this.$refs.addAlert.style.transform = 'translateY(-0vh)'
      },100)
    },
    methods: {
      swipeup(){
        // console.log('--上拉--')
        if(this.currentId <=2){
          this.currentId++
        }
        let num = this.currentId
        this.switchMain(num)
      },
      swipedown(){
        // console.log('--下拉--')
        if(this.currentId >=1){
          this.currentId--
        }
        let num = this.currentId
        this.switchMain(num)
      },
      swiperleft(){
        // console.log("左划")
      },
      swiperright(){
        // console.log("右划")
      },
      menCLick(index){//
        this.currentId = index
        this.switchMain(index)
      },
      maskList(index){//切换下标
        this.currentId = index
        this.switchMain(index)
      },
      //切换
      switchMain(index){
        const INDEXS = index
        const LEN = INDEXS*100
        this.$refs.addAlert.style.transform =  'translateY(-'+LEN+'vh)'
      },
      // 防止抖动
      debounce(func, wait) {
        let timeout;
        return function() {
          let context = this;
          let args = arguments;
          if (timeout) clearTimeout(timeout);
          timeout = setTimeout(() => {
            func.apply(context, args)
          }, wait);
        }
      },
      handleScroll(e) {
        let direction = e.deltaY > 0 ? 'down' : 'up'
        if (direction == 'down'&&this.currentId <=2) {
          this.currentId++
        } else if(direction == 'up'&&this.currentId >=1){
          this.currentId--
        }
        let num = this.currentId
        this.switchMain(num)
      },
    },
    mounted() {
      // 监听鼠标滚动事件
      window.addEventListener('mousewheel', this.debounce(this.handleScroll, 300), true) || window.addEventListener(
        "DOMMouseScroll", this.debounce(this.handleScroll, 300), false)
    },
    destroyed: function () {
      window.removeEventListener('scroll', this.handleScroll);   //  离开页面清除（移除）滚轮滚动事件
      window.removeEventListener('scroll', this.debounce);   //  离开页面清除（移除）滚轮滚动事件
    }
  }
</script>

<style >
  @import url("./index.css");
</style>
