<template>
    <div @click="show=false">
        <my-header></my-header>
        <div class="note">
            <!--文章区域-->
            <div class="post">
                <!--正文-->
                <div class="artical">
                    <h1 class="title">月薪三千，就该去死吗？？？？</h1>
                    <div class="author">
                        <nuxt-link class="avatar" to="/u/123">
                            <img src="~/assets/img/commend4.jpg">
                        </nuxt-link>
                        <div class="info">
                            <span class="name">萌薇</span>
                            <a class="btn-sm" :class="followObj" href="javascript:void(0)" @click="follow"
                               @mouseenter="followIn" @mouseleave="followOut">
                                <i class="fa" :class="iconObj" ref="followBe"></i> <span ref="followWord">关注</span>
                            </a>
                            <div class="meta">
                                <span>2018.01.30 16:09</span>
                                <span>字数 2273</span>
                                <span>阅读 882</span>
                                <span>评论 7</span>
                                <span>喜欢 66</span>
                            </div>
                        </div>
                    </div>
                    <div  class="show-content">
                        <p>01</p>
                        <p>昨晚我失眠了。</p>
                        <p>失眠的原因是看了电影《无问西东》，其中一个场景久久地萦绕于脑中：</p>
                        <p>吴岭澜是影中一位文学天赋极高但理科极差的学生。对于人生，他很少思考过，一味地随着大众的价值认知漂流。</p>
                        <p>当校长梅贻琦问他：“为什么不转去文学系？”时，他这样回答道：</p>
                        <p>“ 最好的学生都是学实科的。我只知道，这个年纪最重要的就是学习，何用管我学什么。每天把自己交给书本，心里就觉得踏实。”</p>
                        <p>梅贻琦答他：</p>
                        <p>“ 你还忽略了一件事，真实。人把自己置身于忙碌当中，有一种麻木的踏实，但丧失了真实。”</p>
                        <p>“什么是真实？”</p>
                        <p>“ 真实就是，你看什么，做什么，和谁在一起，有一种从心灵深处满溢出来的不懊悔、也不羞耻的平和与喜悦。”</p>
                    </div>
                    <div class="show-foot">
                        <nuxt-link to="/nb/123" class="notebook">
                            <i class="fa fa-book"></i>
                            <span>我的文集</span>
                        </nuxt-link>
                        <div class="copyright">
                            &copy;著作版权归彭俊超所有
                        </div>
                    </div>
                    <div class="follow-detail">
                        <div class="info">
                            <nuxt-link class="avatar" to="/u/123">
                                <img src="./../../assets/img/commend4.jpg" alt="">
                            </nuxt-link>
                            <a class="btn" :class="followObj" href="javascript:void(0)" @click="follow"
                               @mouseenter="followIn" @mouseleave="followOut">
                                <i class="fa" :class="iconObj" ref="followBe2"></i> <span ref="followWord2">关注</span>
                            </a>
                            <nuxt-link class="title" to="/u/123">萌薇</nuxt-link>
                            <i class="fa fa-mars"></i>
                            <p>写了 343608 字，被 43225 人关注，获得了 39700 个喜欢</p>
                        </div>
                        <div class="signature">
                            为城市里的不安和孤寂发声
                        </div>
                    </div>
                    <div class="meta-bottom">
                        <div class="like">
                            <div class="btn like-group" ref="likeGroup">
                                <div class="btn-like">
                                    <a href="javascript:void(0)" @click="clickChange()">
                                        <i class="fa fa-heart-o" ref="clickLike"></i>
                                        <span ref="likeWord">喜欢</span>
                                    </a>
                                </div>
                                <div class="modal-wrap" ref="modalWrap">
                                    <a ref="modalNum">126</a>
                                </div>
                            </div>
                        </div>
                        <div class="share-group">
                            <a href="javascript:void(0)" v-b-tooltip.hover title="分享到微信">
                                <i class="fa fa-weibo  weibo"></i>
                            </a>
                            <a href="javascript:void(0)" v-b-tooltip.hover title="分享到微博">
                                <i class="fa fa-weixin weixin"></i>
                            </a>
                            <a href="javascript:void(0)" v-b-tooltip.hover title="分享到qq">
                                <i class="fa fa-qq qq"></i>
                            </a>
                            <a href="javascript:void(0)" class="more-share" @click.stop="show=true">
                                更多分享
                                <div class="shareBox" v-if="show">
                                    <div class="triangleOne"></div>
                                    <div class="triangleTwo"></div>
                                    <div class="triangleThree"></div>
                                    <ul class="showShare">
                                        <li><a href="javascript:void(0)">&#x3000;<i class="fa fa-star" style="color:gold"></i><span>分享到QQ空间</span></a></li>
                                        <li><a href="javascript:void(0)">&#x3000;<i class="fa fa-twitter" style="color:#00aaec"></i><span>分享到witter</span></a></li>
                                        <li><a href="javascript:void(0)">&#x3000;<i class="fa fa-facebook-official" style="color:#4460a0"></i><span>分享到Fcaebook</span></a></li>
                                        <li><a href="javascript:void(0)">&#x3000;<i class="fa fa-google-plus" style="color:#fb6e61"></i></a><span>分享到Google</span></li>
                                        <li><a href="javascript:void(0)">&#x3000;<i class="fa fa-bath" style="color:#30871d"></i></a><span>分享到豆瓣</span></li>
                                    </ul>
                                </div>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
            <!--悬浮的操作框-->
            <div class="side-bar"></div>
            <!--对应的推荐阅读-->
            <div class="note-bottom"></div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        data(){
            return {
                followObj: {
                    'follow': true,
                    'following': false
                },
                iconObj: {
                    'fa-plus-square-o': true,
                    'fa-check': false
                },
                click:true,
                show:false
            }
        },
        components: {
            myHeader
        },
        methods: {
            follow(){
                let word = this.$refs.followWord.innerHTML
                let word2 = this.$refs.followWord2.innerHTML
//
                this.followObj.follow = !this.followObj.follow;
                this.followObj.following = !this.followObj.following;
                this.iconObj['fa-plus-square-o'] = !this.iconObj['fa-plus-square-o'];
                this.iconObj['fa-check'] = !this.iconObj['fa-check']
                this.$refs.followWord.innerHTML = word == '关注' ? '已关注' : '关注'
                this.$refs.followWord2.innerHTML = word2 == '关注' ? '已关注' : '关注'
            },
            followIn(){
                if (this.$refs.followWord.innerHTML == '已关注') {
                    this.$refs.followBe.className = 'fa fa-close';
                    this.$refs.followWord.innerHTML = '取消关注';
                }
                if (this.$refs.followWord2.innerHTML == '已关注') {
                    this.$refs.followBe2.className = 'fa fa-close';
                    this.$refs.followWord2.innerHTML = '取消关注';
                }

            },
            followOut(){
                if (this.$refs.followWord.innerHTML == '取消关注') {
                    this.$refs.followBe.className = 'fa fa-check'
                    this.$refs.followWord.innerHTML = '已关注'
                }
                if (this.$refs.followWord2.innerHTML == '取消关注') {
                    this.$refs.followBe2.className = 'fa fa-check'
                    this.$refs.followWord2.innerHTML = '已关注'
                }
            },
            clickChange(){
                if(this.click == true){
                    this.$refs.likeGroup.style.backgroundColor = '#ea6f5a'
                    this.$refs.modalWrap.style.borderColor = '#fff'
                    this.$refs.modalWrap.style.color = '#fff'
                    this.$refs.clickLike.style.color = '#fff'
                    this.$refs.likeWord.style.color = '#fff'
                    this.$refs.modalNum.innerText++
                }else{
                    this.$refs.likeGroup.style.backgroundColor = '#fff'
                    this.$refs.modalWrap.style.borderColor = '#ea6f5a'
                    this.$refs.modalWrap.style.color = '#ea6f5a'
                    this.$refs.clickLike.style.color = '#ea6f5a'
                    this.$refs.likeWord.style.color = '#ea6f5a'
                    this.$refs.modalNum.innerText--
                }
                this.click = !this.click
            },

        }

    }
</script>