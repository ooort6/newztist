<template>
  <div class="footer">
    <span class="span_1">
      沪ICP备18016391号上海智天信息科技有限公司
    </span>
    <ul>
      <li>
        
        <span><router-link to="/">首页</router-link></span> </li>
      <i>|</i>
       <li>
         <span> <router-link to="/solution">产品与解决方案</router-link></span> </li>
      <i>|</i>
        <li><span> <router-link to="/case">典型案例</router-link></span> </li>
     <i>|</i>
        <li><span> <router-link to="/cooperation">合作发展</router-link></span> </li>
    <i>|</i>
        <li><span> <router-link to="/aboutus">关于我们</router-link></span> </li>
      <i>|</i>
        <li><span> <router-link to="/download">资料下载</router-link></span> </li>
   
    </ul>
    <!-- <div class="sj">
<img src="../assets/image/sjj.png" alt="" style="width:100%;margin-right:1%">

    </div>
    <span class="span_2">
    ：021-80187116
    </span> -->
  </div>
</template>

<script>
export default {
  name: 'Footer',
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.footer{
  min-width: 1500px;
  background: #181828;
  height: 97px;
  width: 100%;
  border-top:1px solid #394050;
  display: flex;
  align-items: center;
  .span_1{
    margin-left: 19%;
    font-size:12px;
font-family:"SourceHanSansCN";
font-weight:300;
color:rgba(255,255,255,1);
line-height:63px;
margin-right: 5%
  }
  .span_2{
    font-size:18px;
font-family:"SourceHanSansCN";
font-weight:500;
color:rgba(255,255,255,1);
line-height:34px;
margin-left: 0.5%;
  }
  ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  align-items: center;
  width: 580px;
  justify-content: space-between;
  margin-right: 3%;
  i{
color:rgba(176,176,176,1);
  }
}
li {
  display: inline-block;
  margin: 0 10px;
  // margin-right: 5%;
  // width: 80px;
  span{
      cursor: pointer;
      font-size:12px;
font-family:"SourceHanSansCN";
font-weight:400;
color:rgba(255,255,255,1);

  }
}
a {

color:rgba(255,255,255,1);

  text-decoration : none ;
}
}
</style>
