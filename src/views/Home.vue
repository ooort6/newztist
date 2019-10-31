<template>
  <div class="home">
    <div class="header1">
      <div class="nav">
        <Header />
      </div>
      <div class="content">
        <p class="p1">
          <!-- Science and technology -->
          SCIENCE AND TECHNOLOGY
        </p>
        <p class="p2">
          <!-- Science and technology -->
          <span class="span_1">智天科技/</span>

          <span class="span_2">大数据分析</span>
        </p>
        <p class="p3">综合运用网络通信、物联网、GIS、大数据分析以及人工智能技术</p>
        <div class="btn_1">
          <span class="span_1">了解详情</span>
        </div>
      </div>
    </div>

    <div class="content">
      <div class="content_l">
        <div class="ll">
          <span class="span_1">
            <span class="span_2"></span>
          </span>
          <span class="span_2">上海智天信息科技</span>
        </div>

        <span class="span_3">
          <p>上海智天信息科技有限公司成立于2012年。2015年通过工信部软件企业评审。通过10年发展，公司业务范围不断扩大，业界知名度不断提升。目前，公司客户群体主要集中在政府、事业单位以及大型企业。</p>
          <p>公司成立之初即以数据分析为核心，经过近10年的研究，逐步构建了3大数据模型：网络数据模型、内容数据模型以及业务数据模型。智天特有的《大数据分析闭环处理》特色，为用户提供从数据采集、到数据分析，并最终对分析结果进行跟踪处置的完整闭环产品。</p>
        </span>
      </div>
      <div class="content_r" v-if="isShow">
        <img class="my-element delay-0.5s" src="../assets/image/anima.png" alt />
      </div>
    </div>

    <div class="fenxi">
    
      <div class="fenxi_1" @click="sx()">
        <img src="../assets/image/sx.png" alt />
        <p class="p_1">网络数据分析</p>
        <p class="p_2">高速网络数据采集及协议解析，实现网络</p>
        <p class="p_2">病毒防护及用户行为分析。</p>
      </div>
      <div class="fenxi_2" @click="nx()">
        <img src="../assets/image/nx.png" alt />
        <p class="p_1">内容数据分析</p>
        <p class="p_2">文本、图像以及视频分析，预警敏感文件或</p>
        <p class="p_2">不良内容。</p>
      </div>
      <div class="fenxi_3" @click="yw()">
        <img src="../assets/image/yw.png" alt />
        <p class="p_1">业务数据分析</p>
        <p class="p_2">通过物联网、大数据分析、人工智能技术、</p>
        <p class="p_2">工作流引擎，实现精细化管理及持续改进。</p>
      </div>
    </div>

    <div class="cp">
      <p class="p_1">智天产品</p>
      <span class="span_1"></span>
      <div class="swip">
        <div class="swiper-container" style="height:100%">
          <div class="swiper-wrapper">

            <div class="swiper-slide" style>
      
               <router-link to="/protect" style="text-decoration: none;">
              <img src="../assets/image/dm.png" style="margin-top:10%;margin-bottom:7%" alt />
              <p class="p_1">恶意代码防护</p>
               </router-link>
            </div>
            <div class="swiper-slide" style>
               <router-link to="/inteldns" style="text-decoration: none;">
              <img src="../assets/image/dns.png" style="margin-top:10%;margin-bottom:7%" alt />
              <p class="p_1">智能DNS</p>
              </router-link>
            </div>
            <div class="swiper-slide" style>
               <router-link to="/erpxt" style="text-decoration: none;">
              <img src="../assets/image/liul.png" style="margin-top:10%;margin-bottom:7%" alt />
              <p class="p_1">网络流量分析及管理</p>
              </router-link>
            </div>
            <div class="swiper-slide" style>
               <router-link to="/examine" style="text-decoration: none;">
              <img src="../assets/image/sh.png" style="margin-top:10%;margin-bottom:7%" alt />
              <p class="p_1">网络内容审核</p>
              </router-link>
            </div>
            <div class="swiper-slide" style>
               <router-link to="/integrated" style="text-decoration: none;">
              <img src="../assets/image/aq.png" style="margin-top:10%;margin-bottom:7%" alt />
              <p class="p_1">安全管理平台</p>
              </router-link>
            </div>
            <div class="swiper-slide" style>
               <router-link to="/others" style="text-decoration: none;">
              <img src="../assets/image/qita.png" style="margin-top:10%;margin-bottom:7%" alt />
              <p class="p_1">其他</p>
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </div>
    <img src="../assets/image/hz.png" style="width:100%;margin-bottom:135px" alt />
    <!-- <Modal v-model="visible" title="Welcome">Welcome to iView</Modal> -->
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";

export default {
  name: "home",
  components: {
    Header
  },
  data() {
    return {
      isShow: false
    };
  },
  watch: {
    //监听路由变化
    $route(to, from) {
      // console.log(to.path, from.path);
      // to , from 分别表示从哪跳转到哪，都是一个对象
      // to.path  ( 表示的是要跳转到的路由的地址 eg: /home );
    }
  },
  mounted() {
    // const element =  document.querySelector('.my-element')
    // element.classList.add('animated', 'bounceInLeft')

    // if(this.isShow){
    const _this = this;
    //console.log(_this.$route.path);
    // if(_this.$route.path=='/'){
    // alert(1)
    $(window).scroll(function() {
      if ($(window).scrollTop() > 750) {
        //code........

        // console.log(_this.$data.isShow);
        _this.$data.isShow = true;
        // debugger;
        if (_this.$data.isShow) {
          const element = document.querySelector(".my-element");
          if (element) {
            // element.classList.remove('animated', "bounceInRight")
          element.classList.remove('animated', "bounceInRight")

            element.classList.add("animated", "bounceInRight");
          }
          // _this.$data.isShow = true;
          //               function handleAnimationEnd() {
          //     element.classList.remove('animated', "bounceInRight")
          // }
        }
      }
      // else{
      //   _this.$data.isShow = true;
      //   console.log(_this.$data.isShow);

      // }
    });
    // }
    // $(window).addEventListener('scroll', handleScroll, false);
    // this.$once('hook:beforeDestroy', () => {
    //   $(window).removeEventListener('scroll', handleScroll, false);
    // })

    $(window).resize(function() {
      //执行代码块

      if ($(window).width() < 1781) {
        _this.$data.isShow = false;
      }
    });
    // }
    var mySwiper = new Swiper(".swiper-container", {
      loop: true,
      autoplay: true,
      // 如果需要分页器
      // 如果需要前进后退按钮
      slidesPerView: 5,
      spaceBetween: 30,
      pagination: {
        el: ".swiper-pagination",
        clickable: true
      }
    });
  },
  methods: {
    show() {
      alert(1);
    },
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
.home {
  min-width: 1500px;
  background: url("../assets/image/bj.png") no-repeat;
  background-size: 100%;

  .header1 {
    height: 953px;
    background: url("../assets/image/st.png") no-repeat;
    background-size: 100% 100%;
    // padding-top: 1rem;

    .nav {
    }
    .content {
      margin-top: 198px;
      margin-left: 379px;
      .p1 {
        font-size: 40px;
        font-family: "SourceHanSansCN";

        // font-weight:100;
        color: rgba(255, 255, 255, 1);
        line-height: 43px;
        margin-bottom: -5px;
      }
      .p2 {
        margin-bottom: 5px;
        .span_1 {
          font-size: 70px;
          font-family: "SourceHanSansCN";
          font-weight: 100;
          color: rgba(255, 255, 255, 1);
          line-height: 101px;
        }

        .span_2 {
          font-size: 70px;
          font-family: "SourceHanSansCN-Heavy";
          color: rgba(255, 255, 255, 1);
          line-height: 101px;
        }
      }
      .p3 {
        font-size: 20px;
        font-family: "SourceHanSansCN";
        font-weight: 400;
        color: rgba(255, 255, 255, 1);
        line-height: 30px;
        margin-bottom: 139px;
      }
      .btn_1 {
        cursor: pointer;
        width: 181px;
        height: 50px;
        background: rgba(6, 118, 205, 1);
        border-radius: 25px;
        display: flex;
        justify-content: center;
        .span_1 {
          font-size: 16px;
          font-family: Adobe Heiti Std;
          font-weight: normal;
          color: rgba(255, 255, 255, 1);
          line-height: 54px;
        }
      }
    }
  }
  .content {
    height: 670px;
    .content_l {
      margin-left: 348px;
      width: 594px;
      // background: red;
      margin-top: 210px;
      float: left;
      .ll {
        margin-bottom: 40px;
        .span_1 {
          width: 136px;
          height: 50px;
          margin-right: 26px;
          float: left;
          display: flex;
          align-items: center;
          .span_2 {
            width: 136px;
            height: 1px;
            background: rgba(163, 231, 240, 1);
          }
        }
        .span_2 {
          display: block;

          font-size: 44px;
          font-family: "SourceHanSansCN";
          font-weight: 400;
          color: rgba(255, 255, 255, 1);
          line-height: 56px;
        }
      }

      .span_3 {
        text-indent: 2em;
        font-size: 18px;
        font-family: "SourceHanSansCN";
        font-weight: 400;
        color: rgba(255, 255, 255, 1);
        line-height: 36px;
      }
    }
  }
  .content_r {
    display: block;
    float: right;
    margin-top: 7%;
  }
  .fenxi {
    display: flex;
    height: 369px;
cursor: pointer;
    .fenxi_1 {
      width: 33%;
      background: #46485c;
      text-align: center;
      padding-top: 3.5%;

      &:hover {
        background: rgba(0, 29, 136, 0.8);
      }
    }
    .p_1 {
      font-size: 28px;
      font-family: "SourceHanSansCN";
      font-weight: 400;
      color: rgba(255, 255, 255, 1);
      line-height: 50px;
      margin-top: 5.6%;
      margin-bottom: 5.2%;
    }
    .p_2 {
      font-size: 20px;
      font-family: "SourceHanSansCN";
      font-weight: 400;
      color: rgba(240, 243, 242, 1);
      line-height: 28px;
    }
    .fenxi_2 {
      width: 33%;
      background: #46485c;
      text-align: center;
      padding-top: 3.5%;
      &:hover {
        background: rgba(145, 86, 191, 0.8);
      }
    }
    .fenxi_3 {
      width: 33%;
      background: #46485c;
      text-align: center;
      padding-top: 3.5%;
      &:hover {
        background: rgba(0, 188, 212, 0.8);
      }
    }
  }

  .cp {
    height: 680px;
    text-align: center;
    padding-top: 94px;
    .p_1 {
      font-size: 42px;
      font-family: Adobe Heiti Std;
      font-weight: normal;
      color: rgba(240, 243, 242, 1);
      line-height: 50px;
      margin-bottom: 36px;
    }
    .span_1 {
      display: block;
      margin: 0 auto;
      width: 87px;
      height: 1px;
      background: rgba(161, 161, 161, 1);
      margin-bottom: 5%;
    }
    .swip {
      width: 80%;
      height: 50%;
      margin: 0 auto;
      img {
        cursor: pointer;
      }
      .p_1 {
        font-size: 24px;
        font-family: PingFang SC;
        font-weight: 500;
        color: rgba(255, 255, 255, 1);
      }
    }
  }
}
</style>
