<template>
    <div>
        <my-header></my-header>
        <div class="my-container">
            <div class="chats">
                <div class="row" style="padding:30px 0;">
                    <div class="aside">
                        <ul>
                            <li><nuxt-link to="/message/comments" class="active">评论</nuxt-link></li>
                            <li><nuxt-link to="/message/chats">简信</nuxt-link></li>
                            <li><nuxt-link to="/message/requests">投稿请求</nuxt-link></li>
                            <li><nuxt-link to="/message/likes">喜欢和赞</nuxt-link></li>
                            <li><nuxt-link to="/message/follows">关注</nuxt-link></li>
                        </ul>
                    </div>
                    <div class="col-xs-16 col-xs-offset-8 main">
                        <div class="menu">全部简信</div>
                        <ul class="jianxin-list">
                            <li>
                                <div class="pull-right">
                                    <span class="time">2017.05.19 16:05</span>&nbsp;
                                    <i class="fa fa-angle-down" @click="downList=!downList"></i>
                                    <ul class="down-list" v-if="downList">
                                        <li>
                                            <a>
                                                <i class="fa fa-trash-o"></i>&#x3000;
                                                <span>删除回话</span>
                                            </a>
                                        </li>
                                        <li>
                                            <a>
                                                <i class="fa fa-ban"></i>&#x3000;
                                                <span>加入黑名单</span>
                                            </a>
                                        </li>
                                        <li>
                                            <a>
                                                <i class="fa fa-flag-o"></i>&#x3000;
                                                <span>举报用户</span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>
                                <nuxt-link class="avatar" to="/u/123">
                                    <img src="~/assets/img/commend4.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="name" to="/u/123">简宝玉</nuxt-link>
                                <nuxt-link class="wrap"  to="/message/chats/123">
                                    <p>  欢迎加入丰富多彩的原创内容社区——简书。有任何疑问（如何投稿，专题主编，签约作者，简叔，简小...</p>
                                </nuxt-link>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        data(){
            return{
                  downList:false,
            }
        },
        mounted() {
            let chatsElement = document.querySelector(".chats .aside ul li:nth-of-type(2)");
            chatsElement.className = "asideCurrent";
        },
        components:{
            myHeader,
        }
    }
</script>
<style>
    .chats{
        position: relative;
    }
    .chats .aside{
        position:fixed;
        top:90px;
        bottom:0;
        width:280px;
        height:500px;
        overflow:hidden;
    }
    .chats li{
        line-height:20px;
    }
    .chats .aside li a{
        padding:10px 25px;
        line-height:30px;
        display: block;
    }
    .chats .aside li:hover{
        background-color:#f0f0f0;
        border-radius:4px;
    }
    /*.chats li a.active{*/
        /*background-color:#f0f0f0;*/
        /*border-radius:4px;*/
    /*}*/
    .chats .main{
        width:625px;
        margin-left:33.3%;
    }
    .chats .main .menu{
        margin-bottom:20px;
        font-weight:700;
        font-size:14px;
    }
    .chats .main .jianxin-list>li{
        border-top:1px solid #f0f0f0;
        position:relative;
        line-height:20px;
    }
    .chats .main .jianxin-list li .pull-right{
        margin:20px 20px 0 0 ;
        font-size:13px;
        color:#9b9b9b;
        position: relative;
    }
    .chats .main .jianxin-list li .pull-right i{
        font-size:18px;
        display: inline-block;
        line-height:10px;
    }
    .chats .main .jianxin-list li .pull-right i:hover{
        cursor: pointer;
    }
    .chats .main .jianxin-list li .pull-right .down-list{
        position: absolute;
        top:20px;
        left:-15px;
        background-color:white;
        box-shadow:0 0 5px #ccc;
        color:#333;
        z-index:1000;
        float:left;
        padding:5px 0;
        margin:2px 0;
        font-size:14px;
        text-align:left;
        border-radius:4px;
    }
    .chats .main .jianxin-list li .pull-right .down-list li a{
        padding:10px 20px;
        font-weight:400;
        white-space: nowrap;
        line-height:40px;
    }
    .chats .main .jianxin-list li .avatar{
        width:48px;
        height:48px;
        margin:20px 10px 20px 20px;
        display: inline-block;
        float:left;
    }
    .chats .main .jianxin-list li .name{
        position: absolute;
        top:25px;
        font-size:15px;
    }
    .chats .main .jianxin-list li .wrap {
        display: block;
        padding: 20px 20px 20px 0;
        min-height: 88px;
    }
    .chats .main .jianxin-list li .wrap p{
        margin:28px 0 0;
        font-size:12px;
        color:#999;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
</style>