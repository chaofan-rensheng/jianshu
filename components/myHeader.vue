<template>
    <div>
        <nav class="navbar navbar-default nav-fixed-top">
            <div class="width-limit">
                <!--logo-->
                <nuxt-link class="nav-logo" to="/"><img src="../assets/img/nav-logo.png" alt=""></nuxt-link>
                <!--写文章-->
                <nuxt-link to="/" class="btn write-btn">
                    <i class="fa fa-edit"></i>写文章
                </nuxt-link>
                <!--登录和注册按钮-->
                <nuxt-link to="/sign-up" class="btn sign-up" style="display: none">注册</nuxt-link>
                <nuxt-link to="/sign-in" class="btn sign-in" style="display: none">登录</nuxt-link>
                <!--如果用户登录，那么显示用户头像-->
                <div style="display:block" class="user"  @mouseover="userShow=true" @mouseleave="userShow=false">
                    <div class="drop-down">
                        <nuxt-link class="avatar" to="/">
                            <img src="../assets/img/my.gif" alt="">
                        </nuxt-link>
                    </div>
                    <div class="drop-menu" v-show="userShow">
                        <ul>
                            <li>
                                <nuxt-link to="/u/132">
                                    <i class="fa fa-home"></i>
                                    我的主页
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/bookmarks">
                                    <i class="fa fa-bookmark"></i>
                                    收藏的文章
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/users/123/like">
                                    <i class="fa fa-heart"></i>
                                    喜欢的文章
                                </nuxt-link>
                            </li>
                            <li >
                                <nuxt-link to="/settings/basic">
                                    <i class="fa fa-cog"></i>
                                    设置
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/">
                                    <i class="fa fa-sign-out"></i>
                                    退出
                                </nuxt-link>
                            </li>
                        </ul>
                    </div>
                </div>
                <!--导航-->
                <div class="my-container">
                    <ul class="nav-list">
                        <li  :class="{active:'' == path}">
                            <nuxt-link to="/">
                                <i class="fa fa-compass"></i>
                                <span>发现</span>
                            </nuxt-link>
                        </li>
                        <li :class="{active:'subscriptions' == path}">
                            <nuxt-link to="/subscriptions">
                                <i class="fa fa-book"></i>
                                <span>关注</span>
                            </nuxt-link>
                        </li>
                        <li class="notify" :class="{active:'message' == path}" @mouseover="notifyShow=true" @mouseleave="notifyShow=false">
                            <nuxt-link to="/message/comments">
                                <i class="fa fa-bell-o"></i>
                                <span >消息</span>
                            </nuxt-link>
                            <div class="drop-menu" v-show="notifyShow">
                                <ul>
                                    <li>
                                        <nuxt-link to="/message/comments">
                                            <i class="fa fa-comment-o"></i>
                                            评论
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/chats">
                                            <i class="fa fa-envelope-o"></i>
                                            简信
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/requests">
                                            <i class="fa fa-upload"></i>
                                            投稿请求
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/likes">
                                            <i class="fa fa-heart-o"></i>
                                            喜欢和赞
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/follows">
                                            <i class="fa fa-user-o"></i>
                                            关注
                                        </nuxt-link>
                                    </li>
                                </ul>
                            </div>
                        </li>
                        <li class="search">
                            <form method="post">
                                <input type="text" @focus="bgShow=true" @blur="bgShow=false" placeholder="搜索">
                                <nuxt-link to="/search" class="search-btn" :class="{active:bgShow}">
                                    <i class="fa fa-search"></i>
                                </nuxt-link>
                            </form>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                userShow:false,
                notifyShow:false,
                bgShow:false,
                path:''
            }
        },
        mounted(){
            this.path = this.$route.path.split('/')[1]
            console.log(this.path)
        },
        name:'myHeader',  //给组件命名
    }
</script>

<style scoped>
    nav{
        height:56px;
        width:100%;
    }
    .navbar{
        padding:0;
        border-bottom:1px solid #e7e7e7;
        margin-bottom:20px;
        background-color:#fff;
    }
    .nav-fixed-top{
        position: fixed;
        top:0;
        left:0;
        z-index: 9999;
    }
    .width-limit{
        min-width:768px;
        width:1440px;
        margin:0 auto;
    }
    .nav-logo{
        float:left;
        height:56px;
        padding:0;
    }
    nav a.write-btn{
        float:right;
        width:100px;
        height:40px;
        margin:7px 15px 0;
        line-height:24px;
        font-size:15px;
        background-color:#ea6f5a;
        color:white !important;
        border-radius:20px;
    }
    nav a.sign-in{
        float:right;
        width:80px;
        height:38px;
        margin:10px 2px 0px 10px;
        line-height:24px;
        font-size:15px;
        color:#969696 !important;
    }
    nav a.sign-up{
        float:right;
        width:80px;
        height:38px;
        margin:10px 0px 0px 2px;
        line-height:24px;
        font-size:15px;
        border:1px solid #ea6f5a;
        border-radius:20px;
        color:#ea6f5a !important;
    }
    nav a.sign-up:focus,nav a.sign-in:focus{
        box-shadow: none !important;
    }
    nav a.sign-up:hover{
        background-color:rgb(254,247,246)
    }
    nav .write-btn:hover{
        background-color:#ec6149;
    }
    nav .user{
        float:right;
        position: relative;
    }
    nav .user .avatar{
        position: relative;
        width:40px;
        height:40px;
        display: block;
        margin:8px 28px 8px 20px;

    }
    nav .user:hover{
        background-color:#f5f5f5;
    }
    nav .user .avatar:before{
        content: "";
        position: absolute;
        top: 18px;
        right: -14px;
        border-left: 5px solid transparent;
        border-right: 5px solid transparent;
        border-top: 6px solid #999;
    }
    nav .user .avatar img{
        width:100%;
        height:100%;
        border-radius:50%;
        border:1px solid #ccc;
    }
    nav .user .drop-menu{
        min-width:160px;
        position: absolute;
        background-color:#fff;
        /*z-index: 1000;*/
        left:0;
        box-shadow: 0 2px 8px rgba(0,0,0,.1);
        font-size:15px;
    }
    nav .user .drop-menu ul{
        /*border:1px solid #ccc;*/
        padding:10px 0;
        margin:0;
    }
    nav .user .drop-menu ul li a{
        padding:10px 20px;
        display:block;
    }
    nav .user .drop-menu ul li a:hover{
        background-color:#f5f5f5;
    }
    nav .user .drop-menu ul li i{
        margin-right:15px;
        color:#ea6f5a;
        font-size:18px;
    }
    nav .nav-list{
        margin:0 -15px;
        padding:0;
    }
    nav .nav-list:after{
        /*overflow: hidden;*/
        /*zoom: 1;*/
        content:'';
        clear: both;
        height:0;
        display: block;
        visibility: hidden;
    }
    nav .nav-list>li{
        float: left;
        margin-right:5px;
    }
    nav .nav-list>li>a{
        display: block;
        height:55px;
        padding:15px;
        margin-right:15px;
        font-size:17px;
    }
    nav .nav-list>li a  i{
        margin-right:7px;
        font-size:20px;
        margin-top:5px;
        text-align: center;
    }
    nav .nav-list>li.active{
        color:#ea6f5a;
        background-color:white !important;
    }
    nav .nav-list>li.active .drop-menu li{
        color:#333;
    }
    nav .nav-list>li:hover{
        background-color:#f5f5f5;
    }
    nav .nav-list .search{
        padding-left:15px;
    }
    nav .nav-list .search form{
        position: relative;
        margin-top:9px;
    }
    nav .nav-list .search form input{
        width:240px;
        height:38px;
        border:none;
        border-radius:20px;
        background-color:#eee;
        padding:0 30px 0 20px;
        font-size:15px;
        transition:width 1s ease-in;
    }
    nav .nav-list .search form input:focus{
        width:320px;
    }

    nav .nav-list .search:hover{
        background-color:white;
    }
    nav .nav-list .search form a.search-btn{
        display: block;
        position: absolute;
        right:10px;
        top:4px;
        width:30px;
        height:30px;
        line-height:30px;
        text-align: center;
    }
    nav .nav-list .search form a.search-btn i{
        font-size:18px;
        position: relative;
        left:3px;
    }
    nav .nav-list .search form a.active{
        background-color:#969696 !important;
        border-radius:50%;
        color:white !important;
    }
    nav .nav-list .notify{
        position: relative;

    }
    nav .notify .drop-menu{
        min-width:160px;
        position: absolute;
        left:0;
        box-shadow: 0 2px 8px rgba(0,0,0,.1);
        font-size:15px !important;
        background-color:white;
        z-index: 9999;
    }
    nav .notify .drop-menu ul{
        /*border:1px solid #ccc;*/
        padding:10px 0;
        margin:0;
    }
    nav .notify .drop-menu ul li a{
        padding:10px 20px;
        display:block;
    }
    nav .notify .drop-menu ul li a:hover{
        background-color:#f5f5f5;
    }
    nav .notify .drop-menu ul li i{
        margin-right:15px;
        color:#ea6f5a;
        font-size:18px;
    }

    @media(max-width:1440px){
        nav .nav-list>li>a>i{
            display: none;
        }
        nav .nav-list .search form input{
            width:160px;
        }

        nav .nav-list .search form input:focus{
            width:240px;
        }

    }

    @media(max-width:1080px){
        nav .nav-list>li>a{
            margin-right:0;
        }

        nav .nav-list>li>a>i {
            display: block;
        }
        nav .nav-list>li>a>span{
            display: none;
        }

        nav .nav-list .search form input{
            width:150px;
        }

        nav .nav-list .search form input:focus{
            width:150px;
        }
    }


    @media (max-width:768px){
        nav .nav-list{
            display: none;
        }
    }
</style>