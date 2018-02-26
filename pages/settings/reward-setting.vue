<template>
  <div>
   <my-header></my-header>
   <div class="setting my-container">
       <div class="row">
           <div class="aside col-4">
            <my-setting></my-setting>
           </div>
           <div class="main col-8">
             <table>
                 <tbody>
                     <tr class="clearfix"> 
                         <td class="setting-title pull-left">赞赏功能</td>
                         <td>
                            <div class="col-xs-2">
                                <input type="radio" name="yen" checked>
                                <span>开启</span>
                            </div>
                            <div class="col-xs-8">
                                <input type="radio" name="yen">
                                <span>关闭</span>
                            </div>
                            <p>开启后赞赏按钮将出现在你的文章底部</p>
                         </td>
                     </tr>
                     <tr class="clearfix">
                       <td class="setting-title pull-left top-padding">赞赏描述</td>
                       <td class="top-padding">
                         <textarea rows="3"></textarea>
                       </td>
                     </tr>
                 </tbody>
             </table>
             <button class="save">保存</button>
           </div>
       </div>
   </div>
  </div>
</template>
<script>
import myHeader from "~/components/myHeader";
import mySetting from "~/components/mySetting";
export default {
  name:'basic',
   mounted(){
   let dom1=document.querySelector('.aside ul li:nth-of-type(5)');
   dom1.className="asideActive";
  },
  components:{
      myHeader,
      mySetting
  }
}
</script>
<style scoped>
.setting .main tr{
    border-bottom: 1px solid #f0f0f0;
}
.setting .main tr:last-child{
    border: none;
}
.setting-title{
    font-size: 15px;
    color: #969696;
    line-height: 26px;
}
.setting .main span{
    margin: 0 20px 0 6px;
    font-size: 15px;
}
.setting .main p{
    padding-top: 8px;
    font-size: 12px;
    color: #969696;
}
.setting .main .top-padding{
    padding-top: 20px;
}
.setting .main textarea{
    width: 100%;
    height: 100px;
    margin-bottom: 10px;
    padding: 8px 10px ;
    font-size: 15px;
    border: 1px solid #c8c8c8;
    border-radius: 4px;
    resize: none;
    background-color: #f7f7f7;
    outline-style: none;
}
.save{
    width: 100px;
    margin: 30px 0 60px;
    border-radius: 20px;
    border: none;
    color: #fff;
    padding: 6px 12px;
    background-color: #42c02e;
}
table{
    width:625px;
}
.col-xs-2{
    display: inline-block;
    width: 25%;
}
.col-xs-8{
    display: inline-block;
    width: 75%;
}
@media (max-width: 1080px) {
    table{
        width: 485px;
    }
}
</style>
