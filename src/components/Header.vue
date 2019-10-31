<template>
  <div class="header">
     <div id="nav">
      <div class="logo">
        <img src="../assets/image/logo.png" alt="">
      </div>
      <div class="nav_r">
  <router-link to="/">首页</router-link> 
      <router-link to="/solution">产品解决方案</router-link>
       <router-link to="/case">典型案例</router-link>
        <router-link to="/cooperation">合作发展</router-link>
         <router-link to="/aboutus">关于我们</router-link>
          <router-link to="/download">资料下载</router-link>
      </div>
    
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

#nav {
  padding: 30px 0 10px 0;
  // position: absolute;
  top: 0;
  width: 72.97%;
  // background: red;
  border-bottom: 1px solid #A6F7FE;
  margin: 0 auto;
  padding-top: 4%;
  .logo{
    float: left;
    margin-left: 5%;
    height: 10px;
    display:flex;
    justify-content: center;
    align-items: center;

  }
  .nav_r{
    height: 30px;
    margin-left: 30.98%;
// float: right;
// display: flex;
// display: flex;
// justify-content: center;
// align-items: center;
// flex-flow: nowrap;

  a {
  font-size:18px;
font-family:Source Han Sans CN;
font-weight:500;
color:rgba(255,255,255,1);
margin-right: 7%;
    text-decoration : none ;
    &.router-link-exact-active {
      color: #00ECFF;
    }
  }
  }
  // left: 30%;

}
</style>
