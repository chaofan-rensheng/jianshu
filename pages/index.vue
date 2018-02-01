<template>
    <div>
        <my-header></my-header>
        <div class="index my-container">
            <div class="row">
                <div class="col-8 main">
                    <!--轮播-->
                    <div v-swiper:mySwiper="swiperOption" class="banner">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide" v-for="banner in banners">
                                <img :src="banner">
                            </div>
                        </div>
                        <div class="swiper-pagination swiper-pagination-white"></div>
                        <div class="swiper-button-next swiper-button-white"></div>
                        <div class="swiper-button-prev swiper-button-white"></div>
                    </div>
                    <!--推荐专题-->
                    <div class="recommend-collection">
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend5.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend1.png" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend2.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend3.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend5.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend4.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend6.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/commend6.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123" class="more-hot-collection">
                            更多热门专题
                            <i class="fa fa-chevron-right"></i>
                        </nuxt-link>
                    </div>
                    <div class="split-line"></div>
                    <!--文章列表-->
                    <div class="list-container">
                        <ul class="note-list">
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/pic.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/touxiang.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">萌薇</nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        如何把书中的知识转化成能力？这是我见过的最好的回答
                                    </nuxt-link>
                                    <p class="abstract">
                                        随着知识经济的兴起，读书的重要性得到了大家的普遍认同，于是市场上出现很多读书方法，比如速度、多读、慢读、列读……不管你采用哪一种读书方法，最终都要回归到“行动”二字上，正如陆...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/collection/123" class="tag">
                                            <i class="fa fa-eye">579</i>
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment">200</i>
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart">546</i>
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/touxiang.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">萌薇</nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        如何把书中的知识转化成能力？这是我见过的最好的回答
                                    </nuxt-link>
                                    <p class="abstract">
                                        随着知识经济的兴起，读书的重要性得到了大家的普遍认同，于是市场上出现很多读书方法，比如速度、多读、慢读、列读……不管你采用哪一种读书方法，最终都要回归到“行动”二字上，正如陆...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/collection/123" class="tag">
                                            <i class="fa fa-eye">579</i>
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment">200</i>
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart">546</i>
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/pic.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/touxiang.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">萌薇</nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        如何把书中的知识转化成能力？这是我见过的最好的回答
                                    </nuxt-link>
                                    <p class="abstract">
                                        随着知识经济的兴起，读书的重要性得到了大家的普遍认同，于是市场上出现很多读书方法，比如速度、多读、慢读、列读……不管你采用哪一种读书方法，最终都要回归到“行动”二字上，正如陆...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/collection/123" class="tag">
                                            <i class="fa fa-eye">579</i>
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment">200</i>
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart">546</i>
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/touxiang.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">萌薇</nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        如何把书中的知识转化成能力？这是我见过的最好的回答
                                    </nuxt-link>
                                    <p class="abstract">
                                        随着知识经济的兴起，读书的重要性得到了大家的普遍认同，于是市场上出现很多读书方法，比如速度、多读、慢读、列读……不管你采用哪一种读书方法，最终都要回归到“行动”二字上，正如陆...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/collection/123" class="tag">
                                            <i class="fa fa-eye">579</i>
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment">200</i>
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart">546</i>
                                        </span>
                                    </div>
                                </div>
                            </li>
                        </ul>
                    </div>
                    <!--阅读更多-->
                    <nuxt-link class="load-more" to="/">
                        阅读更多
                    </nuxt-link>
                </div>
                <div class="col-4 aside">
                    <div class="board">
                        <nuxt-link to="/">
                            <img src="../assets/img/1.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/2.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/3.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/4.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/5.png" alt="">
                        </nuxt-link>
                    </div>
                    <nuxt-link  to="/" class="download">
                        <img src="../assets/img/lianxi.jpg" alt="">
                    </nuxt-link>
                    <div class="recommend-author">
                        <div class="title">
                            <span>推荐作者</span>
                            <a   href="javascript:void(0)" class="page-change"  @click="rotate()"><i  ref="refresh" class="fa fa-refresh"></i>换一批</a>
                        </div>
                        <ul class="list">
                            <li>
                                <nuxt-link to="/u/123" class="avatar">
                                    <img src="../assets/img/touxiang.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    <i class="fa fa-plus-square-o"></i>关注
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    占小狼
                                </nuxt-link>
                                <p>
                                    写了152.9千字·7.2k喜欢
                                </p>
                            </li>
                            <li>
                                <nuxt-link to="/u/123" class="avatar">
                                    <img src="../assets/img/touxiang.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    <i class="fa fa-plus-square-o"></i>关注
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    占小狼
                                </nuxt-link>
                                <p>
                                    写了152.9千字·7.2k喜欢
                                </p>
                            </li>
                            <li>
                                <nuxt-link to="/u/123" class="avatar">
                                    <img src="../assets/img/touxiang.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    <i class="fa fa-plus-square-o"></i>关注
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    占小狼
                                </nuxt-link>
                                <p>
                                    写了152.9千字·7.2k喜欢
                                </p>
                            </li>
                            <li>
                                <nuxt-link to="/u/123" class="avatar">
                                    <img src="../assets/img/touxiang.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    <i class="fa fa-plus-square-o"></i>关注
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    占小狼
                                </nuxt-link>
                                <p>
                                    写了152.9千字·7.2k喜欢
                                </p>
                            </li>
                        </ul>
                        <nuxt-link to="/" class="find-more">查看全部 <i class="fa fa-angle-right"></i></nuxt-link>
                    </div>
                </div>
            </div>
        </div>
        <footer class="my-container">
            <div class="row">
                <div class="col-8">
                    <ul class="footer-list">
                        <li>关于简书</li> ·
                        <li>联系我们</li> ·
                        <li>加入我们</li> ·
                        <li>简书出版</li> ·
                        <li>品牌与徽标</li> ·
                        <li>帮助中心</li> ·
                        <li>合作伙伴</li>
                    </ul>
                    <div class="foot-info">
                        <span>©2012-2018 上海佰集信息科技有限公司 / 简书 / 沪ICP备11018329号-5 /</span>
                        <img src="../assets/img/shiming.png" alt="">
                        <nuxt-link to="/">沪公网安备31010402002252号 / </nuxt-link>
                        <img src="" alt="">
                        <span>举报电话：021-34770013 /</span>
                        <img src="" alt="">
                    </div>
                </div>
            </div>
        </footer>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        data () {
            return {
                banners: [ '/banner1.jpg', '/banner2.jpg', '/banner3.jpg' ],
                swiperOption: {
                    autoplay:{
                      dalay:3000,  //切换时间
                      stopOnlastSlide:true,   //是否停止在最后一张
                      disableOnInteraction:false,  //禁止轮播
                    },
                    pagination: {
                        el: '.swiper-pagination',
                        clickable:true
                    },
                    navigation:{
                        nextEl:'.swiper-button-next',
                        prevEl:'.swiper-button-prev'
                    }
                },
                deg:-360
            }
        },
        components:{
            myHeader
        },
        methods:{
            rotate(){
                this.deg = this.deg + 360
                this.$refs.refresh.style.transform = `rotate(${this.deg + 360}deg)`
            }
        }
    }
</script>
<style>
    .swiper-button-next{
        background-color:rgb(0,0,0,0.4);
    }
    .swiper-button-prev{
        background-color:rgb(0,0,0,0.4)
    }
</style>
