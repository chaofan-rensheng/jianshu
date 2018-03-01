<template>
    <div>
        <!--<div class="comment-placeholder">-->
            <!--<div class="author">-->
                <!--<div class="avatar"></div>-->
                <!--<div class="info">-->
                    <!--<div class="name"></div>-->
                    <!--<div class="meta"></div>-->
                <!--</div>-->
            <!--</div>-->
            <!--<div class="title"></div>-->
            <!--<div class="title animated-delay"></div>-->
            <!--<div class="tool-group">-->
                <!--<i class="fa fa-thumbs-up"></i>-->
                <!--<div class="zan"></div>-->
                <!--<i class="fa fa-comment"></i>-->
                <!--<div class="like"></div>-->
            <!--</div>-->
        <!--</div>-->
        <ul class="note-list">
            <li class="artical">
                <div class="content">
                    <div class="author">
                        <nuxt-link to="/u/123" class="avatar">
                            <img src="~/assets/img/commend4.jpg" alt="">
                        </nuxt-link>
                        <div class="info">
                            <nuxt-link class="name" to="/u/123">北纬90度旅行</nuxt-link>
                            <span>02.05 21:46</span>
                        </div>
                    </div>
                    <nuxt-link to="/u/123" class="title">
                        你是否为你月薪3K的时候感到骄傲
                    </nuxt-link>
                    <p class="abstract">
                        当我月薪3K的时候，我第一次见到那么多的钱，我应经不知道该如何去花了
                    </p>
                    <div class="meta">
                        <nuxt-link to="/u/123">
                            <i class="fa fa-eye"></i>&nbsp;4
                        </nuxt-link>
                        <nuxt-link to="/u/123">
                            <i class="fa fa-comment"></i>&nbsp;1
                        </nuxt-link>
                        <span>
                            <i class="fa fa-heart"></i>&nbsp;1
                        </span>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
    export default{
        data(){
            return{

            }
        }
    }
</script>
<style>
    .person .list-container .note-list .artical .author{
        margin:0;
    }
    .person .list-container .note-list .artical .info span{
        display: inline-block;
        padding-left:3px;
        color:#969696;
    }
    .person .list-container .note-list .artical .title{
        margin:-7px 0 10px;
        font-size:18px;
        font-weight:700;
    }
    .person .list-container .note-list .artical .abstract{
        margin:0px 0px 8px;
        font-size:13px;
        line-height:24px;
    }
    .person .list-container .note-list .artical .meta a{
        margin-right:10px;
        color:#b4b4b4 !important;
        font-size: 14px;
    }
</style>