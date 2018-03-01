<template>
    <div>
        <div class="comment-placeholder">
            <div class="author">
                <div class="avatar"></div>
                <div class="info">
                    <div class="name"></div>
                    <div class="meta"></div>
                </div>
            </div>
            <div class="title"></div>
            <div class="title animated-delay"></div>
            <div class="tool-group">
                <i class="fa fa-thumbs-up"></i>
                <div class="zan"></div>
                <i class="fa fa-comment"></i>
                <div class="like"></div>
            </div>
        </div>
        <ul class="note-list">
            <li class="dynamic">
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
                    <p class="comment">说的针对</p>
                    <div class="blockquote">
                        <nuxt-link to="/u/123">捂着心脏撕心裂肺的想_7f88</nuxt-link>&nbsp;<span>评论自</span>
                        <nuxt-link to="/u/123">你是否为你月薪3K的时候感到骄傲</nuxt-link>
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
    .person .list-container .note-list .dynamic .author{
        margin-bottom:14px;
    }
    .person .list-container .note-list  .dynamic .info span{
        display: inline-block;
        padding-left:3px;
        color:#969696;
    }
    .person .list-container .note-list  .dynamic .blockquote{
        border-left:3px solid #d9d9d9;
        color:#969696;
        padding:10px 20px;
        font-size:12px;
        margin:0 0 20px;
    }
    .person .list-container .note-list  .dynamic .blockquote a{
        color:#3194d0 !important;
        margin-right:5px;
    }
</style>