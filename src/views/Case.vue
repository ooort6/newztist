<template>
  <div class="case">
    <div class="header1">
      <div class="nav">
        <Header />
      </div>
    </div>
    <div class="banner">
      <ul>
        <li
          v-for="(item,index) in items"
          :key="item.id"
          @click="activeShow(index)"
          :class="{active:index==ins}"
        >{{item.id}}</li>
        <!-- <li>企业</li>
        <li>运营商</li>
        <li>教育</li>-->
      </ul>
    </div>
    <div class="content1" v-if="ins==0">
      <p class="p_1">上海市某区政务网</p>
      <div class="content_2">
        <a href="#">实施背景</a>
        <p class="p_2">拥有主机约2000台，20多台服务器。</p>
        <p class="p_2">由国内知名安全公司的专业维护团队进行网络安全及运行维护。</p>
      </div>
      <div class="content_2">
        <a href="#">项目目标</a>
        <p class="p_2">验证网络是否安全。是否存在僵尸网络病毒。</p>
        <p class="p_2">如果存在病毒，提供相关杀毒软件进行查杀。</p>
      </div>

      <div class="content_2">
        <a href="#">系统上线</a>
        <p class="p_2">上线当月即检测出约6%主机及1台DNS服务器已被木马/僵尸网络控制。证明网络存在安全风险。</p>
        <p class="p_2">提供病毒验证及查杀工具，培训专业维护团队进行应急处置。快速消除木马/僵尸网络。</p>
      </div>

      <div class="content_2">
        <a href="#">运行效果</a>
        <p class="p_2">本系统为维护团队提供了必要的技术手段，及时发现中毒机器，减少网络安全风险。</p>
        <p class="p_2">系统一处部署，全网防护。操作简单，安全可靠，成本降低，效率提升优势明显。</p>
      </div>

      <div class="content_3">
        <span class="span_1">相关产品</span>
        <img src="../assets/image/xz.png" style="margin-right:1%" alt />
        <span class="span_2">恶意代码防护系统</span>
      </div>
    </div>

    <div class="content1" v-if="ins==1">
      <p class="p_1">上海信产通信服务有限公司</p>
      <div class="content_2">
        <a href="#">实施背景</a>

        <p class="p_2">业务内容繁多，建立体验式营销场馆。</p>
        <p class="p_2">为实现沉浸式业务体验场景，现场使用大量传感器、智能设备以及媒体播放设备。</p>
      </div>
      <div class="content_2">
        <a href="#">项目目标</a>
        <p class="p_2">精简现场设备操作人员，体现运营商在IT技术领域的先进性。</p>
        <p class="p_2">能根据业务体验者所属行业不同，快速调度全馆所有设备的内容。</p>
      </div>

      <div class="content_2">
        <a href="#">系统上线</a>
        <p class="p_2">采用物联网、设备接口调用、嵌入式系统开发等，实现馆内全部电器设备统一接入及控制。实现全场一人操作。</p>
        <p class="p_2">开发智能设备专用AGENT，采用服务器统一管理全部演示内容，实现全馆内容一键切换。</p>
      </div>

      <div class="content_2">
        <a href="#">运行效果</a>
        <p class="p_2">系统运行稳定可靠，未出现过软件BUG导致系统控制失败的故障。系统良好的可扩展性，新设备类型可方便接入系统。</p>
        <p class="p_2">降低系统操作维护成本，全馆近千台设备仅需一人操作。</p>
      </div>

      <div class="content_3">
        <span class="span_1">相关产品</span>
        <img src="../assets/image/xz.png" style="margin-right:1%" alt />
        <span class="span_2">综合控制系统</span>
      </div>
    </div>

    <div class="content1" v-if="ins==2">
      <p class="p_1">中国电信股份有限公司</p>
      <div class="content_2">
        <a href="#">实施背景</a>
        <p class="p_2">某国际知名高科技公司，在中国境内有近百个体验店以及业务分支机构。使用多家运营商网络接入Internet。</p>
        <p class="p_2">存在店内体验用户访问不良网站的情况，不利于产品体验式销售。</p>
      </div>
      <div class="content_2">
        <a href="#">项目目标</a>
        <p class="p_2">屏蔽对不良网站的访问。网内的体验用户和工作人员使用不同的管理策略。</p>
      </div>

      <div class="content_2">
        <a href="#">系统上线</a>
        <p class="p_2">所有对域名黑名单的访问均被截获，跳转至指定网站。根据访问者所处的物理位置给出最佳的目标IP地址解析。</p>
      </div>

      <div class="content_2">
        <a href="#">运行效果</a>
        <p class="p_2">系统部署简单。费用省，可扩展性强。使用运营商云服务器。轻松实现一次部署，全国所有门店使用。</p>
        <p class="p_2">操作简单方便。不需要增加额外人员进行系统的管理维护。</p>
      </div>

      <div class="content_3">
        <span class="span_1">相关产品</span>
        <img src="../assets/image/xz.png" style="margin-right:1%" alt />
        <span class="span_2">网络内容审核系统</span>
      </div>
    </div>

    <div class="content1" v-if="ins==3">
      <p class="p_1">上海市某区教育局</p>
      <div class="content_2">
        <a href="#">实施背景</a>
        <p class="p_2">
                            教育部发文要求做好各中小学的安全工作。上海市教委要求各区教育局完成安全管理中心建设工作。
                        </p>
        <p class="p_2">
某区教育局无专门安全管理信息系统。安全工作处理效率、管理手段、安全责任到位方面存在较多问题。

        </p>
      </div>
      <div class="content_2">
        <a href="#">项目目标</a>
        <p class="p_2">
                            安全管理工作信息化。安全资产、危险隐患动态管理。安全工作考核量化和科学化。
                        </p>
        <p class="p_2">
良好的可扩充性，与已有系统对接。开放接口，方便后续建设安防系统接入，避免信息孤岛。


        </p>
      </div>

      <div class="content_2">
        <a href="#">系统上线</a>
        <p class="p_2">
                            实现安全管理工作相关公文流转、隐患上报、隐患处置工作闭环。
                        </p>
        <p class="p_2">
日常安全巡检工作制度化，工作任务内容明确。使用移动APP执行巡检任务，数据上报及时。


        </p>
      </div>

      <div class="content_2">
        <a href="#">运行效果</a>
        <p class="p_2">
                            系统完成安全工作的分析统计，实现安全工作的智能预警及处理。
                        </p>
        <p class="p_2">
基于地理信息的管理界面以及图形化统计界面，直观易懂，管理便捷高效。

        </p>
      </div>

      <div class="content_3">
        <span class="span_1">相关产品</span>
        <img src="../assets/image/xz.png" style="margin-right:1%" alt />
        <span class="span_2">安全管理平台</span>
      </div>
    </div>
  </div>
</template>
<script>
import Header from "@/components/Header.vue";
export default {
  name: "case",
  components: {
    Header
  },
  data() {
    return {
      items: [
        { id: "政府" },
        { id: "企业" },
        { id: "运营商" },
        { id: "教育" }
        //  { id: "自助导览系统" }
      ],
      ins: 0
    };
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
    activeShow(index) {
      this.ins = index;
    }
  }
};
</script>
<style lang="scss" scoped>
.case {
  min-width: 1500px;
  background: #181828;
  .header1 {
    height: 420px;
    background: url("../assets/image/anli1.png") no-repeat;
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
      cursor: pointer;
      // &:hover {
      //   background: rgba(159, 215, 252, 1);
      //   color: #174db0;
      //   cursor: pointer;
      // }
    }
    .active {
      background: rgba(159, 215, 252, 1);
      color: #174db0;
      cursor: pointer;
    }
  }
  .content1 {
    height: 920px;
    width: 74%;
    // background: red;
    margin: 0 auto;
    padding-top: 4.78%;
    .p_1 {
      font-size: 30px;
      font-family: PingFang SC;
      font-weight: 500;
      color: rgba(255, 255, 255, 1);
      display: block;
      margin-bottom: 4%;
    }
    .content_2 {
      margin-bottom: 4%;
      a {
        font-size: 20px;
        font-family: PingFang SC;
        font-weight: 500;
        color: rgba(255, 255, 255, 1);
        display: block;
        margin-bottom: 1%;
      }
      .p_2 {
        font-size: 18px;
        font-family: PingFang SC;
        font-weight: 400;
        color: rgba(255, 255, 255, 1);
        margin-bottom: 0.4%;
      }
    }
    .content_3 {
      display: flex;
      align-items: center;
      .span_1 {
        display: flex;
        width: 87px;
        height: 28px;
        background: #00bcd4;
        justify-content: center;
        align-items: center;
        color: #fff;
        font-size: 18px;
        font-family: PingFang SC;
        float: left;
        margin-right: 1%;

        // font-weight:500;
        // color:rgba(255,255,255,1);
      }
      .span_2 {
        font-size: 20px;
        font-family: PingFang SC;
        font-weight: bold;
        color: rgba(255, 255, 255, 1);
      }
    }
  }
}
</style>