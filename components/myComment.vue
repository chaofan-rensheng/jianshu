<template>
    <div>
        <div id="comment-list" class="comment-list">
            <!--提交的留言表单-->
            <form action="" class="new-comment">
                <nuxt-link class="avatar" to="/u/123">
                    <img src="../assets/img/commend4.jpg" alt="">
                </nuxt-link>
                <textarea @focus="send=true" placeholder="请写下你的评论" v-model="value"></textarea>
                <transition :duration="200"  name="fade">
                    <div v-if="send" class="write-function-block clearfix">
                        <div class="emoji-modal-wrap" >
                            <a href="javascript:void(0)" class="emoji" @click="showEmoji=!showEmoji">
                                <i class="fa fa-smile-o"></i>
                            </a>
                            <transition  name="fade">
                                <div v-if="showEmoji" class="emoji-modal arrow-up">
                                    <vue-emoji @select="selectEmoji"></vue-emoji>
                                </div>
                            </transition>
                        </div>
                        <div class="hint">Ctrl+Enter 发表</div>
                        <a href="javascript:void(0)" class="btn btn-send" @click="sendDate">发送</a>
                        <a href="javascript:void(0)" class="cancel" @click="send=false">取消</a>
                    </div>
                </transition>
            </form>
            <!--留言列表-->
            <div id="normal-comment-list" class="normal-comment-list">
                <!--留言的排序-->
                <div class="top-title">
                    <span>25条评论</span>
                    <a class="author-only" href="javascript:void(0)">只看作者</a>
                    <div class="pull-right">
                        <a class="active" href="javascript:void(0)">按喜欢排序</a>
                        <a href="javascript:void(0)">按时间正序</a>
                        <a href="javascript:void(0)">按时间倒序</a>
                    </div>
                </div>
                <!--留言的正文-->
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
                <div :id="'comment-' + comment.id" class="comment" v-for="(comment,index) in comments">
                    <div class="comment-content">
                        <div class="author">
                            <nuxt-link to="/u/123" class="avatar" >
                                <img :src="comment.user.avatar" alt="">
                            </nuxt-link>
                            <div class="info">
                                <nuxt-link class="name" to="/u/123">{{comment.user.nick_name}}</nuxt-link>
                                <div class="meta"><span>{{comment.floor}}楼&nbsp;·&nbsp;{{comment.create_at|formatDate}}</span></div>
                            </div>
                        </div>
                        <div class="comment-wrap">
                            <p>{{comment.compiled_content}}</p>
                            <div class="tool-group">
                                <a href="javascript:void(0)">
                                    <i class="fa fa-thumbs-o-up" :id="'like'+comment.id"></i>
                                    <span>{{comment.likes_count}}人点赞</span>
                                </a>
                                <a href="javascript:void(0)">
                                    <i class="fa fa-comment-o"></i>
                                    <span>回复</span>
                                </a>
                            </div>
                        </div>
                    </div>
                    <div v-if="comment.children.length != 0" class="sub-comment-list">
                        <div class="sub-comment" v-for="(subComment,index) in comment.children" :id=" 'comment-' + subComment.id ">
                            <p>
                                <nuxt-link to="/u/123">{{subComment.user.nick_name}}</nuxt-link>:
                                <span v-html="subComment.compiled_content"></span>
                            </p>
                            <div class="sub-tool-group">
                                <span>{{subComment.create_at|formatDate}}</span>
                                <a href="javascript:void(0)">
                                    <i class="fa fa-comment-o"></i>
                                    <span>回复</span>
                                </a>
                            </div>
                        </div>
                        <div class="more-comment">
                            <a href="javascript:void(0)" class="add-comment-btn" @click="showSubCommentForm(index)">
                                <i class="fa fa-pencil"></i>
                                <span ref="newPingLun">添加新评论</span>
                            </a>
                        </div>
                        <!--要显示的表单-->
                        <transition :duration="200"  name="fade">
                            <form class="new-comment" v-if="activeIndex.includes(index)" style="margin-left:0">
                                <textarea v-focus placeholder="写下你的评论"></textarea>
                                    <div v-if="" class="write-function-block clearfix">
                                        <div class="emoji-modal-wrap">
                                            <a href="javascript:void(0)" class="emoji" @click="showSubEmoji(index)">
                                                <i class="fa fa-smile-o"></i>
                                            </a>
                                            <transition  name="fade">
                                                <div v-if="emojiIndex.includes(index)" class="emoji-modal arrow-up">
                                                    <vue-emoji ref="emoji" @select="selectEmoji"></vue-emoji>
                                                </div>
                                            </transition>
                                        </div>
                                        <div class="hint">Ctrl+Enter 发表</div>
                                        <a href="javascript:void(0)" class="btn btn-send" @click="sendSubCommentData(index)">发送</a>
                                        <a href="javascript:void(0)" class="cancel" @click="closeSubComment(index)">取消</a>
                                    </div>
                            </form>
                        </transition>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import vueEmoji from '~/components/vueEmoji'
    export default{
        name:'myComment',
        data(){
            return{
                send:false,
                showEmoji:false,
                value:'',
                comments:[
                    {
                        id:19935725,
                        floor:2,
                        like:true,
                        likes_count:20,
                        note_id:2305472,
                        user_id:6780849,
                        user:{
                            avatar:'/commend4.jpg',
                            id:6780849,
                            is_author:false,
                            nick_name:'月薪三千不知道怎么花',
                            badge:null,
                        },
                        create_at:"2016-10-20T23:23:16.000+08:00",
                        children_count:3,
                        compiled_content: "祝贺你😀",
                        children:[
                            {
                                id:20116365,
                                user_id:2604707,
                                user:{
                                    id:2604707,
                                    nick_name:'Bowman'
                                },
                                parent_id:19965725  ,
                                create_at:'2016-10-20T23:23:16.000+08:00',
                                compiled_content:'兄die,我也是和你 一样的困惑，甚至一度迷失自我',
                            },
                            {
                                id:20116300,
                                user_id:2604700,
                                user:{
                                    id:2604700,
                                    nick_name:'qiangsef'
                                },
                                parent_id:19965725  ,
                                create_at:'2018-12-20T23:23:16.000+08:00',
                                compiled_content:'为什么我的枪法 老是比别人的好的多'
                            },
                            {
                                id:20122300,
                                user_id:2622700,
                                user:{
                                    id:2622700,
                                    nick_name:'hong'
                                },
                                parent_id:19965725  ,
                                create_at:'2016-12-20T23:23:16.000+08:00',
                                compiled_content:'当月薪达到三千之后，我已经迷茫了，那么多的钱，我真的不知道该如何花完'
                            }
                        ]
                    },
                    {
                        id:20005109,
                        floor: 3,
                        like:false,
                        likes_count:4,
                        note_id:23234187,
                        user_id:10211267,
                        user:{
                            avatar:'/commend4.jpg',
                            id:10211267,
                            is_atthor:false,
                            nick_name:"细雨绵绵残花落",
                        },
                        create_at:"2018-01-27T09:08:21.000+08:00",
                        children_count:1,
                        compiled_content: "真好，一段情，一双人，一辈子",
                        children:[
                            {
                                id:20116365,
                                user_id:2604707,
                                user:{
                                    id:2604707,
                                    nick_name:'冷眼'
                                },
                                parent_id:20005109  ,
                                create_at:"2018-01-27T09:41:24.000+08:00",
                                compiled_content:'兄die,我也是和你 一样的困惑，甚至一度迷失自我'
                            },
                        ]
                    },
                    {
                        id:20005111,
                        floor: 4,
                        like:false,
                        likes_count:5,
                        note_id:23234112,
                        user_id:10211255,
                        user:{
                            avatar:'/commend4.jpg',
                            id:10211244,
                            is_atthor:false,
                            nick_name:"风飘票",
                        },
                        create_at:"2018-05-27T09:08:21.000+08:00",
                        children_count:0,
                        compiled_content: "这位老哥是真的刘辟",
                        children:[
                            {
                                id:20116365,
                                user_id:2604707,
                                user:{
                                    id:2604707,
                                    nick_name:'冷眼'
                                },
                                parent_id:20005109  ,
                                create_at:"2018-01-27T09:41:24.000+08:00",
                                compiled_content:'兄die,我也是和你 一样的困惑，甚至一度迷失自我'
                            },
                        ]
                    }
                ],
                activeIndex:[],
                emojiIndex:[],
            }
        },
        components:{
            vueEmoji
        },
        directives: {
            // 除了默认设置的核心指令( v-model 和 v-show ),Vue 也允许注册自定义指令。
            // 对纯 DOM 元素进行底层操作
            // 注册局部指令，在模板中任何元素上使用新的 v-focus 属性
            "focus": {
                // 钩子函数：bind inserted update componentUpdated unbind
                // 钩子函数的参数：el，binding，vnode，oldVnode
                bind:function(el,binding,vnode,oldVnode){
                    el.focus();
                },
                inserted: function (el) {
                    // 聚焦元素
                    el.focus()
                }
            }
        },
        methods:{
            selectEmoji(code){
                this.showEmoji = false;
                this.value += code
            },
            sendDate(){
                console.log('测试数据是否发送')
            },
            showSubCommentForm(value){
                if(this.activeIndex.includes(value)){
                    let index = this.activeIndex.indexOf(value);
                    this.activeIndex.splice(index,1);
                }else{
                    this.activeIndex.push(value);
                }
            },
            showSubEmoji:function(value){
                if(this.emojiIndex.includes(value)){
                    this.emojiIndex = [];
                }else{
                    this.emojiIndex = [];
                    this.emojiIndex.push(value);
                }
            },
            sendSubCommentData:function(value){
                let index = this.activeIndex.indexOf(value);
                this.activeIndex.splice(index,1);
            },
            closeSubComment:function(value){
                let index = this.activeIndex.indexOf(value);
                this.activeIndex.splice(index,1);
            },
        }
    }
</script>
<style>


    .fade-enter-active,.fade-leave-active {
        opacity: 1;
        transition: .3s;
        -webkit-transition: .3s
    }
    .fade-enter,.fade-leave-to {
        opacity: 0;
        transform: translate3d(0,-5%,0);
        -webkit-transform: translate3d(0,-5%,0);
        transition: .3s;
        -webkit-transition: .3s
    }
    .note .post .comment-list{
        padding-top:20px;
    }
    .note .post .comment-list .new-comment{
        position: relative;
        margin-left:48px;
        margin-bottom:20px;
    }
    .note .post .comment-list .avatar{
        width:38px;
        height:38px;
        display: inline-block;
        margin-right:5px;
    }
    .note .post .comment-list .new-comment .avatar{
        position: absolute;
        left:-48px;
    }
    .note .post .comment-list .new-comment textarea{
        width:100%;
        height:80px;
        padding:10px 15px;
        border-radius:4px;
        display: inline-block;
        vertical-align: top;
        outline-style: none;
        font-size:13px;
        resize: none;
        background-color:#f8f8f8;
        border: 1px solid #dcdcdc;
    }
    .note .post .comment-list .new-comment .emoji-modal-wrap{
        position: relative;
    }
    .note .post .comment-list .new-comment .emoji{
        float:left;
        margin-top:14px;
    }
    .note .post .comment-list .new-comment .emoji i {
        font-size:25px;
        color:#969696;
    }
    .note .post .comment-list .new-comment .emoji i:hover{
        color:#2f2f36;
    }
    .note .post .comment-list .new-comment .hint{
        float:left;
        margin:20px 0 0 20px;
        font-size:13px;
        color:#969696;
    }
    .note .post .comment-list .new-comment .cancel{
        float:right;
        font-size:16px;
        margin:18px 30px 0 0 ;
        color:#969696 !important;
    }
    .note .post .comment-list .new-comment .cancel:hover{
        color: #2f2f36 !important;
    }
    .note .post .comment-list .new-comment .btn-send{
        float:right;
        width:78px;
        padding:8px 18px;
        margin:10px 0;
        font-size:18px;
        background:#42c02e;
        border-radius:20px;
        color:#fff !important;
        box-shadow:none;

    }
    .note .post .comment-list .new-comment .btn-send:hover{
        background-color:#3db922;
    }
    .note .post .comment-list .new-comment .emoji-modal-wrap .emoji-modal{
        position: absolute;
        top:50px;
        left:-48px;
        width:402px;
        height:208px;
        padding:10px;
        border:1px solid #d9d9d9;
        border-radius:4px;
        box-shadow: 0px 5px 25px rgba(0,0,0,0.1);
        z-index: 101;
        background-color:#ffff;
    }
    .arrow-up:after{
        content:'';
        display: inline-block;
        position: absolute;
        left:48px;
        top:-1px;
        width:15px;
        height:15px;
        border-left:1px solid #d9d9d9;
        border-top:1px solid #d9d9d9;
        transform:translate3d(0,-50%,0)  rotate(45deg);
        background-color:#fff;
    }
    .note .post .comment-list .normal-comment-list{
        margin-top:30px;
    }
    .note .post .comment-list .top-title{
        padding-bottom:20px;
        border-bottom:1px solid #f0f0f0;
    }
    .note .post .comment-list .top-title span{
        font-size:17px;
        font-weight:700;
    }
    .note .post .comment-list .top-title .author-only{
        font-size:12px;
        padding:4px 8px;
        border:1px solid #e1e1e1;
        border-radius:12px;
        color:#969696 !important;
        margin-left:10px;
    }
    .note .post .comment-list .top-title .pull-right a{
        margin-left:10px;
        font-size:12px;
        color: #969696 !important;
    }
    .note .post .comment-list .top-title .pull-right a.active{
        color: #2f2f2f !important;
    }
    .note .post .comment-list .comment{
        padding:20px 0 30px 0;
        border-bottom:1px solid #f0f0f0;
    }
    .note .post .comment-list .comment .author{
        margin-bottom:15px;
    }
    .note .post .comment-list .comment .info{
        display: inline-block;
        vertical-align: middle;
    }
    .note .post .comment-list .info .name{
        font-size:15px;
    }
    .note .post .comment-list .info .meta{
        font-size:12px;
        color:#969696;
    }
    .note .post .comment-list .comment p{
        font-size:16px;
        margin:10px 0;
        line-height:1.5;
        word-break: break-all;
    }
    .note .post .comment-list .comment .tool-group a{
        color:#969696 !important;
        margin-right:10px;
    }
    .note .post .comment-list .comment .tool-group a i{
        margin-right:5px;
        font-size:18px;
    }
    .note .post .comment-list .comment .tool-group a span{
        font-size:14px;
    }
    .note .post .comment-list .sub-comment-list{
        border-left:2px solid #d9d9d9;
        margin-top:20px;
        padding:5px 0 5px 20px;
    }
    .note .post .comment-list .sub-comment{
        padding-bottom:15px;
        margin-bottom:15px;
        border-bottom:1px dashed #f0f0f0;
    }
    .note .post .comment-list .sub-comment p{
        font-size:14px;
        line-height:1.5;
        margin-bottom:5px;
    }
    .note .post .comment-list .sub-comment p a{
        color:#3194d0 !important;
    }
    .note .post .comment-list .sub-tool-group{
        font-size:12px;
        color:#969696;
    }
    .note .post .comment-list .sub-tool-group a{
        margin-left:10px;

    }
    .note .post .comment-list .sub-tool-group a i{
        margin-right:5px;
    }
    .note .post .comment-list .more-comment{
        font-size:14px;
        color:#969696;
        padding-bottom:15px!important;
        margin-bottom:15px!important;
    }
    .note .post .comment-list .more-comment a:hover{
        color: #333333 !important;
    }
    .note .post .comment-list .more-comment i{
        margin-right:5px;
    }
    .note .post .comment-list .addNew-comment .new-comment{
        margin-left:0;
    }

</style>
