<template>
  <div class="download">
    <div class="header1">
      <div class="nav">
        <Header />
      </div>
      <div class="content1">

      </div>
    </div>

    <!-- <div class="content3">
  
    </div> -->
  </div>
</template>
<script>
import Header from "@/components/Header.vue";
export default {
  name: "download",
  components: {
    Header
  },
  data() {
    return {};
  },
  watch: {
    //监听路由变化
    $route(to, from) {
      // to , from 分别表示从哪跳转到哪，都是一个对象
      // to.path  ( 表示的是要跳转到的路由的地址 eg: /home );
    }
  },
  mounted() {
    const _this = this;
  },
  methods: {
    // activeShow(index) {
    //   this.ins = index;
    // }
  }
};
</script>
<style lang="scss" scoped>
.download {
  min-width: 1500px;
  background: #181828;
  .header1 {
    height: 1000px;
    background: url("../assets/image/bi1.png") no-repeat;
    background-size: 100% 110%;
    // padding-top: 1rem;
    .content1{
      height: 200px;
      background: red;
    }
  }

  // .content3 {
  //   height: 2020px;
  //   // width: 74%;
  //   // background: red;
  //   margin: 0 auto;
  //   padding-top: 4.78%;
  //   // text-align: center;
    
  // }
}
</style>