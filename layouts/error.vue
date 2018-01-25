<template>
  <section>
    <div v-if="error.statusCode === 404">
      <nuxt-link to="/" class="long-logo"><img src="../assets/img/long-logo.png" alt=""></nuxt-link>
      <div class="error">
        <div class="error-block"><img src="../assets/img/404-2.png" alt=""></div>
        <h3>你要找的页面不存在</h3>
        <div class="sub-title">可能是因为你的链接地址有误，该文章已经被作者删除或转为私密状态。</div>
        <nuxt-link to="/" class="follow">返回「简书」首页</nuxt-link>
      </div>
    </div>
    <div v-if="error.statusCode === 500">
      <nuxt-link to="/" class="long-logo"><img src="../assets/img/long-logo.png" alt=""></nuxt-link>
      <div class="error">
        <div class="error-block"><img src="../assets/img/500.jpg" alt=""></div>
        <h3>你要找的页面不存在</h3>
        <div class="sub-title">可能是因为你的链接地址有误，该文章已经被作者删除或转为私密状态。</div>
        <nuxt-link to="/" class="follow">返回「简书」首页</nuxt-link>
      </div>
    </div>
    <!--<h1 class="title">-->
    <!--{{ error.statusCode }}-->
    <!--</h1>-->
    <!--<h2 class="info">-->
    <!--{{ error.message }}-->
    <!--</h2>-->
    <!--<nuxt-link class="button" to="/" v-if="error.statusCode === 404">-->
    <!--&lt;!&ndash;Homepage&ndash;&gt;-->
    <!--</nuxt-link>-->
  </section>
</template>
<script>
    export default {
        props: ['error']
    }
</script>

<style scoped>
  section a.long-logo{
    position: absolute;
    left:40px;
    top:40px;
    /*width:300px;*/
    height:41px;
    display: block;
  }
  .error{
    width:100%;
    max-width:1440px;
    margin:0 auto;
    text-align:center;
  }
  .error .error-block{
    padding-top:80px;
    padding-bottom:20px;
  }
  .error .error-block img{
    width:220px;
    margin:0 auto;
  }
  /*.title*/
  /*{*/
  /*margin-top: 15px;*/
  /*font-size: 5em;*/
  /*}*/
  /*.info*/
  /*{*/
  /*font-weight: 300;*/
  /*color: #9aabb1;*/
  /*margin: 0;*/
  /*}*/
  h3{
    margin:40px 0 20px 0;
    font-weight:bold;
    font-size:20px;
  }
  .error .sub-title{
    margin:10px 0px 30px 0;
    font-size:14px;
  }
  .error .follow{
    padding:13px 0;
    width:160px;
    font-size:15px;
    border-radius:40px;
    background-color:#42C02E;
    border:1px solid #42C02E;
    display: inline-block;
    cursor: pointer;
    text-align: center;
    vertical-align: middle;
  }
  .error .follow:hover{
    background-color:#28a014;
  }
  @media (max-width:768px) {
    .long-logo{
      display: none;
    }
  }
</style>
