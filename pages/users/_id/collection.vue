<template>
    <div>
        <my-header></my-header>
        <div class="my-container person">
            <div class="row">
                <div class="col-xs-16 main" style="width:640px;">
                    <div class="main-top">
                        <a class="avatar" href="javascript:void(0)">
                            <img src="~/assets/img/commend4.jpg" alt="">
                        </a>
                        <a class="commonStyle"  :class="followStyle ? 'beFollow' : 'unBeFollow'"
                           href="javascript:void(0)"  @click="followMe()" @mouseenter="followEnter()" @mouseleave="followLeave()" >
                            <i class="fa" :class="followClass ? 'fa-plus' : 'fa-check' " ref="followClose"></i>&nbsp;<span ref='followWord'>关注</span>
                        </a>
                        <nuxt-link class="easyMessage commonStyle" to="/u/123" >发简信</nuxt-link>
                        <div class="title">
                            <a  class="name" href="#">北纬90度旅行</a>
                        </div>
                        <div class="info">
                            <ul>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/u/123">
                                            <p>6</p>关注 <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/u/123">
                                            <p>4</p>粉丝 <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/u/123">
                                            <p>1</p>文章 <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/u/123">
                                            <p>33</p>字数
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block" style="border:none">
                                        <nuxt-link to="/u/123">
                                            <p>1</p>收获喜欢
                                        </nuxt-link>
                                    </div>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <ul class="person-menu">
                        <li :class="{active:currentTab == 'FollowCollection'}" @click="toggleTab('FollowCollection')">
                            <a href="javascript:void(0)">
                                <i class="fa fa-file-text"></i>我关注的专题/文集/连载
                            </a>
                            <div class="bottomLine"></div>
                        </li>
                        <li :class="{active:currentTab == 'LikeArticle'}" @click="toggleTab('LikeArticle')">
                            <a href="javascript:void(0)">
                                <i class="fa fa-bell"></i>我喜欢的文章
                            </a>
                            <div class="bottomLine"></div>
                        </li>
                    </ul>
                    <div class="list-container">
                        <keep-alive>
                            <component :is="currentTab"></component>
                        </keep-alive>
                    </div>
                </div>
                <div class="col-xs-7 col-xs-offset-1 aside">
                    <div class="title">个人介绍</div>
                    <a href="javascript:void(0)" class="edit" @click="showTextarea=true">
                        <i class="fa fa-pencil"></i>&nbsp;编辑
                    </a>
                    <form action="" v-show="showTextarea">
                        <textarea></textarea>
                        <div class="save">保存</div>
                        <div class="cancel" @click="showTextarea=false">取消</div>
                    </form>
                    <hr style="margin-top:40px;">
                    <ul class="list">
                        <li>
                            <nuxt-link to="/users/123/collection">
                                <i class="fa fa-th-large"></i>
                                <span>我关注的专题/文集/连载</span>
                            </nuxt-link>

                        </li>
                        <li>
                            <nuxt-link to="/users/123/like">
                                <i class="fa fa-heart-o"></i>
                                <span>我喜欢的文章</span>
                            </nuxt-link>
                        </li>
                    </ul>
                    <div>
                        <div>
                            <div class="title">我创建的专题</div>
                            <nuxt-link to="/collections/new" target="_blank" class="plus">
                                <i class="fa fa-plus"></i>&nbsp;
                                <span>新建专题</span>
                            </nuxt-link>
                            <ul class="list">
                                <li>
                                    <nuxt-link to="/u/123"><img src="~/assets/img/crop.png" alt=""></nuxt-link>
                                    <nuxt-link to="/u/123">面试</nuxt-link>
                                </li>
                            </ul>
                        </div>
                        <div>
                            <div class="title">我的文集</div>
                            <ul class="list">
                                <li>
                                    <nuxt-link to="/u/123"><i class="fa fa-book" style="color:#b4b4b4;"></i>记事本</nuxt-link>
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
    import FollowCollection from '~/components/users/FollowCollection'
    import LikeArticle from '~/components/users/LikeArticle'
    export default{
        data(){
            return{
                currentTab:'FollowCollection',
                showTextarea:false,
                followClass:true,
                followStyle:true
            }
        },
        components:{
            myHeader,
            FollowCollection,
            LikeArticle,
        },
        methods:{
            toggleTab(tab){
                this.currentTab = tab
            },
            followMe(){
                this.followClass = !this.followClass
                this.followStyle = !this.followStyle
                if(this.followClass == false){
                    this.$refs.followWord.innerHTML = '已关注'
                }else{
                    this.$refs.followWord.innerHTML = '关注'
                }
            },
            followEnter(){
                if(this.$refs.followWord.innerHTML == '已关注'){
                    this.$refs.followWord.innerHTML = '取消关注'
                    this.$refs.followClose.classList.add('fa-close')
                }
            },
            followLeave(){
                if(this.$refs.followWord.innerHTML == '取消关注'){
                    this.$refs.followWord.innerHTML = '已关注'
                    this.$refs.followClose.classList.remove('fa-close')
                }
            }
        }
    }
</script>