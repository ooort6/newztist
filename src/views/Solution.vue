<template>
  <div class="solution">
    <div class="header1">
      <div class="nav">
        <Header />
      </div>
    </div>
    <div class="banner">
      <ul>
        <li @click="sx()">网络数据分析</li>
        <li @click="nx()">内容数据分析</li>
        <li @click="yw()">业务内容分析</li>
        <li @click="$router.push({name:'others'})">其他</li>
      </ul>
    </div>
    <div class="content">
      <p class="p_1">—— 智天大数据处理架构 ——</p>
      <div class="content_1">
        <div>
          <img src="../assets/image/s11.png" alt />
          <p class="p_2">人员、组织数据</p>
          <p class="p_2">（人工采集）</p>
        </div>
        <div>
          <img src="../assets/image/s22.png" alt />
          <p class="p_2">网络数据</p>
          <p class="p_2">（流量监听）</p>
        </div>
        <div>
          <img src="../assets/image/s33.png" alt />
          <p class="p_2">生产安全</p>
          <p class="p_2">（物联网 设备接口）</p>
        </div>
        <div>
          <img src="../assets/image/s44.png" alt />
          <p class="p_2">运营数据</p>
          <p class="p_2">（软件系统集成）</p>
        </div>
        <div>
          <img src="../assets/image/s55.png" alt />
          <p class="p_2">外部环境数据</p>
          <p class="p_2">（物联网）</p>
        </div>
      </div>
       <p class="p_3">—— 智天大数据产品矩阵 ——</p>
       <p class="p_4">引入AI推理机制，实现数据分析结果的智能应用及系统的持续演进</p>
    <img src="../assets/image/s77.png" alt="">
      <p class="p_5">—— 大数据处理业务系统 ——</p>
       <p class="p_4">业内领先的AI安全推理机制，实现安全风险的积累及自学习</p>
       <img src="../assets/image/s444.png" alt="">
    </div>
  </div>
</template>
<script>
import Header from "@/components/Header.vue";
export default {
  name: "solution",
  components: {
    Header
  },
    watch:{   //监听路由变化
    $route( to , from ){   
       console.log( to , from )
        // to , from 分别表示从哪跳转到哪，都是一个对象
        // to.path  ( 表示的是要跳转到的路由的地址 eg: /home );
     }

},
mounted(){
   const _this = this;
   console.log(_this.$route.path)
},
methods:{
      sx(){
      this.$router.push({path:'/networkda'})
    },
     nx(){
      this.$router.push({path:'/contentda'})
    },
     yw(){
      this.$router.push({path:'/businessda'})
    }
}
};
</script>
<style lang="scss" scoped>
.solution {
  min-width: 1500px;
  background: #181828;
  .header1 {
    height: 688px;
    background: url("../assets/image/st1.png") no-repeat;
    background-size: 100% 100%;
    // padding-top: 1rem;
  }
  .banner {
    height: 68px;
    background: #00bcd4;
    ul {
      list-style-type: none;
      padding: 0;
      display: flex;
      align-items: center;
      width: 80%;
      margin: 0 auto;
      justify-content: space-between;
      height: 100%;
    }
    li {
      display: flex;
      margin: 0 10px;
      justify-content: center;
      align-items: center;
      width: 100%;
      font-size: 24px;
      height: 100%;
      font-family: "SourceHanSansCN";
      font-weight: 400;
      color: rgba(255, 255, 255, 1);
      line-height: 40px;
      &:hover {
        background: rgba(159, 215, 252, 1);
        color: #174db0;
        cursor: pointer;
      }
    }
  }
  .content {
    height: 2020px;
    text-align: center;
    .p_1 {
      font-size: 36px;
      font-family: "SourceHanSansCN";
      font-weight: 500;
      color: rgba(255, 255, 255, 1);
      line-height: 12px;
      margin-top: 6.5%;
      margin-bottom: 4%;
    }
    .p_3 {
      font-size: 36px;
      font-family: "SourceHanSansCN";
      font-weight: 500;
      color: rgba(255, 255, 255, 1);
      line-height: 12px;
      margin-top: 4.5%;
      margin-bottom: 2%;
    }
    .p_4{
      font-size:24px;
      font-family: "SourceHanSansCN";
font-weight:400;
color:rgba(221,221,221,1);
  margin-bottom: 3.5%;
    }
      .p_5 {
      font-size: 36px;
      font-family: "SourceHanSansCN";
      font-weight: 500;
      color: rgba(255, 255, 255, 1);
      line-height: 12px;
      margin-top: 8%;
      margin-bottom: 2%;
    }
    .content_1 {
      // background: red;
      width: 80%;
      height: 410px;
      margin: 0 auto;
      display: flex;
      justify-content: center;
      align-items: center;
      .p_2 {
        font-size: 24px;
        font-family: "SourceHanSansCN";
        font-weight: 500;
        color: rgba(255, 255, 255, 1);
      }
    }
  }
}
</style>