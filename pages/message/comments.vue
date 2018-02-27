<template>
    <div>
        <my-header></my-header>
        <div class="my-container">
            <div class="comments">
                <div class="row" style="padding:30px 0;">
                    <div class="aside">
                    <ul>
                        <li><nuxt-link to="/message/comments">评论</nuxt-link></li>
                        <li><nuxt-link to="/message/chats">简信</nuxt-link></li>
                        <li><nuxt-link to="/message/requests">投稿请求</nuxt-link></li>
                        <li><nuxt-link to="/message/likes">喜欢和赞</nuxt-link></li>
                        <li><nuxt-link to="/message/follows">关注</nuxt-link></li>
                    </ul>
                </div>
                    <div class="col-xs-16 col-xs-offset-8 main" style="margin-left:55px">
                        <div>
                            <div class="menu">收到的评论</div>
                            <ul class="comment-list">
                                <li>
                                    <nuxt-link to="/u/123" class="avatar">
                                        <img src="~/assets/img/commend4.jpg" alt="">
                                    </nuxt-link>
                                    <div class="info">
                                        <div>
                                            <nuxt-link to="/u/123" class="user">
                                                捂着心脏撕心裂肺的想_7f88
                                            </nuxt-link>
                                            <span class="commment-slogan">评论了你的文章</span>
                                           <nuxt-link to="/u/123" class="artical-title">《你是否为你月薪3K的时候感到骄傲》</nuxt-link>
                                        </div>
                                        <div class="time">2018.02.05 21:47</div>
                                    </div>
                                    <p>说的针对</p>
                                    <div class="meta">
                                        <nuxt-link to="/u/123">
                                            <i class="fa fa-comment-o"></i>&nbsp;
                                            <span>回复</span>
                                        </nuxt-link>
                                        <nuxt-link to="/u/123">
                                            <i class="fa fa-share"></i>&nbsp;
                                            <span>查看对话</span>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <nuxt-link to="/u/123" class="avatar">
                                        <img src="~/assets/img/commend4.jpg" alt="">
                                    </nuxt-link>
                                    <div class="info">
                                        <div>
                                            <nuxt-link to="/u/123" class="user">
                                                欢喜非喜
                                            </nuxt-link>
                                            <span class="commment-slogan">在文章</span>
                                            <nuxt-link to="/u/123" class="artical-title">《大家都质问我，为什么过年不回家》</nuxt-link>
                                            <span>中写了一条新评论</span>
                                        </div>
                                        <div class="time">2018.02.05 21:47</div>
                                    </div>
                                    <p>说的针对</p>
                                    <div class="meta">
                                        <nuxt-link to="/u/123">
                                            <i class="fa fa-comment-o"></i>&nbsp;
                                            <span>回复</span>
                                        </nuxt-link>
                                        <nuxt-link to="/u/123">
                                            <i class="fa fa-share"></i>&nbsp;
                                            <span>查看对话</span>
                                        </nuxt-link>
                                    </div>
                                </li>
                            </ul>
                        </div>
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

            }
        },
        mounted() {
            let commentsElement = document.querySelector(".comments .aside ul li");
            commentsElement.className = "asideCurrent";
        },
        components:{
            myHeader,
        }
    }
</script>
<style>
    .aside{
        position:flex;
        top:0;
        bottom:0;
        width:280px;
        height:500px;
        overflow:hidden;
    }
    .comments .aside li{
        line-height:20px;
    }
    .comments .aside li a{
        padding:10px 25px;
        line-height:30px;
        display: block;
    }
    .comments .aside li:hover{
        background-color:#f0f0f0;
        border-radius:4px;
    }
    /*.comments .aside li a.active{*/
        /*background-color:#f0f0f0;*/
        /*border-radius:4px;*/
    /*}*/
    .comments .main {
        width:625px;
    }
    .comments .main .menu{
        margin-bottom:20px;
        font-size:17px;
        font-weight:700;
    }
    .comments .main .comment-list li{
        width:100%;
        padding:20px;
        border-top:1px solid #f0f0f0;
    }
    .comments .main .comment-list .avatar{
        width:40px;
        height:40px;
        display: inline-block;
        margin-right:5px;
    }
    .comments .main .comment-list li .info{
        display: inline-block;
        width:535px;
        vertical-align: top;
        font-size:15px;
    }
    .comments .main .comment-list li .info .user{
        margin-right:5px;
        color:#333;
    }
    .comments .main .comment-list li .info .artical-title{
        color:#3194d0 !important;
    }
    .comments .main .comment-list li .info .time{
        margin-top:2px;
        font-size:12px;
        color:#969696;
    }
    .comments .main .comment-list li p{
        margin:10px 0 0 ;
        font-size:15px;
        line-height:1.7;
    }
    .comments .main .comment-list li .meta{
        margin-top:10px;
        height:20px;
    }
    .comments .main .comment-list li .meta a{
        display: inline-block;
        margin-right:30px;
        font-size:13px;
        color:#969696 !important;
    }
</style>