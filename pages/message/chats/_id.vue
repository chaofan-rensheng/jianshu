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
                        <div class="chat-top">
                            <nuxt-link to="/message/chats" class="chatsBack">
                                <i class="fa fa-hand-o-left"></i>&nbsp;返回简信列表
                            </nuxt-link>
                            <b>与简宝玉的对话</b>
                            <i class="fa fa-angle-down chatslist" @click="chatsList=!chatsList"></i>
                            <ul class="down-list" v-if="chatsList">
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
                        <div class="message-show">
                            <ul class="message-list">
                                <li class="message-l">
                                    <nuxt-link to="/u/123" class="avatar">
                                        <img src="~/assets/img/commend7.png" alt="">
                                    </nuxt-link>
                                    <div>
                                        <span class="content">
                                             欢迎加入丰富多彩的原创内容社区——简书。有任何疑问
                                            （如何投稿，专题主编，签约作者，简叔，简小妹……），请点击此链接查看
                                             或关注微信公众号简宝玉（jianshubaoyu）并留言。
                                            <a href="http://www.jianshu.com/p/27de765cdb28"
                                               rel="nofollow" target="_blank">http://www.jianshu.com/p/27de765cdb28</a>
                                        </span>
                                    </div>
                                    <span class="time">2017.05.19 16:05</span>
                                </li>
                                <li class="message-r">
                                    <nuxt-link to="/u/123" class="avatar">
                                        <img src="~/assets/img/commend1.png" alt="">
                                    </nuxt-link>
                                    <div>
                                        <span class="content">
                                            你好，宝玉，我是吃鸡王
                                        </span>
                                    </div>
                                    <span class="time">03.01 15:49</span>
                                </li>
                            </ul>
                        </div>
                        <div class="write-message">
                            <form>
                                <textarea type="text" placeholder="输入内容" class="form-control"></textarea>
                                <input type="submit"  value="发送" class="btn btn-send">
                            </form>
                            <div class="hint">Enter 直接发送</div>
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
                chatsList:false,
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
    .chats .main{
        width:625px;
        margin-left:33.3%;
    }
    .chats .main .chat-top{
        position: fixed;
        width: 625px;
        z-index: 1;
        min-height: 35px;
        margin-bottom: 20px;
        padding-bottom: 10px;
        text-align: center;
        background-color: #fff;
        border-bottom: 1px solid #f0f0f0;
    }
    .chats .main .chat-top .chatsBack{
        position: absolute;
        top: 4px;
        left: 0;
        font-size: 14px;
        color: #969696 !important;
    }
    .chats .main .chat-top b{
        display: inline-block;
        padding: 0 140px 0 160px;
        font-size: 14px;
        font-weight:700;
    }
    .chats .main .chat-top .chatslist{
        position: absolute;
        top: 0;
        right: 15px;
        font-weight:400;
        font-size:24px;
        cursor: pointer;
    }
    .chats .main .chat-top .down-list{
        position: absolute;
        top:20px;
        right:15px;
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
    .chats .main .chat-top .down-list li a{
        padding:10px 20px;
        font-weight:400;
        white-space: nowrap;
        line-height:40px;
    }
    .chats .main .message-show{
        margin-top:60px;
    }
    .chats .main .message-show  .avatar{
        display: block;
        float:left;
        width:40px;
        height:40px;
        cursor: pointer;
    }
    .chats .main .message-show .message-l .avatar img{
        width:100%;
        height:100%;
        border:1px solid #ddd;
        border-radius:50%;
    }
    .chats .main .message-show .message-l div{
        position: relative;
        display: block;
        margin: 4px 56px 0;
        min-height: 39px;
    }
    .chats .main .message-show li div{
        position: relative;
        display: block;
        margin: 4px 56px 0;
        min-height: 39px;
    }
    .chats .main .message-show  div .content{
        position: relative;
        padding: 8px 12px;
        font-size: 14px;
        border: 1px solid;
        word-break: break-word!important;
        word-break: break-all;
        line-height: 1.5;
        display: table-cell;
    }
    .chats .main .message-show .message-l div .content{
        min-height: 39px;
        background-color: #e7f1fc;
        border-color: #bad0e9 !important;
        border-radius: 0 4px 4px 4px;
    }
    .chats .main .message-show .message-r div .content{
        float: right;
        min-height: 39px;
        background-color: #eee;
        border-color: #d9d9d9;
        border-radius: 4px 0 4px 4px;
    }
    .chats .main .message-show li div:before,.chats .main .message-show li div:after{
        position: absolute;
        top: 0;
        content: "";
        display: inline-block;
    }
    .chats .main .message-show li div:after{
        top:1px;
    }
    .chats .main .message-show .message-l div:before,.chats .main .message-show .message-l div:after{
        left: -9px;
        border-left: 9px solid transparent;
        border-top: 16px solid #bad0e9;
    }
    .chats .main .message-show .message-l div:after{
        left: -7px;
        border-top: 16px solid #e7f1fc;
    }
    .chats .main .message-show .time{
        margin-top: 2px;
        font-size: 12px;
        color: #d9d9d9;
    }
    .chats .main .message-show  .message-l .time{
        margin-left:56px;
    }
    .chats .main .message-show .message-r .avatar {
        float: right;
    }
    .chats .main .message-show .message-r div:before,.chats .main .message-show .message-r div:after{
        right: -9px;
        border-right: 9px solid transparent;
        border-top: 16px solid #d9d9d9;
    }
    .chats .main .message-show .message-r div:after{
        right: -7px;
        border-top: 16px solid #eee;
    }
    .chats .main .message-show .message-r .time{
        float:right;
        margin-right:16px;
    }
    .chats .main .write-message{
        position: fixed;
        bottom: 0;
        width: 100%;
        margin-top: 15px;
        background-color: #fff;
    }
    .chats .main .write-message form{
        max-width:625px;
    }
    .chats .main .write-message form{
        margin:0 0 20px;
    }
    .chats .main .write-message form .form-control{
        background-color: hsla(0,0%,71%,.1);
        width: 100%;
        padding: 6px 12px;
        background-image: none;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-shadow: inset 0 1px 1px rgba(0,0,0,.075);
        transition: border-color .15s ease-in-out,box-shadow .15s ease-in-out;
    }
    .chats .main .write-message .hint{
        padding-top: 3px;
        font-size: 13px;
        color: #969696;
    }
    .chats .main .write-message .btn-send{
        float: right;
        width: 78px;
        margin: 10px 0;
        padding: 8px 18px;
        font-size: 16px;
        border: none;
        border-radius: 20px;
        color: #fff;
        background-color: #42c02e;
        cursor: pointer;
        outline: none;
        display: block;
    }
</style>