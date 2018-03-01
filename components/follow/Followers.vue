<template>
    <div>
        <ul class="user-list">
            <li>
                <a href="javascript:void(0)" class="avatar">
                    <img src="~/assets/img/my.gif" alt="">
                </a>
                <div class="info">
                    <a href="javascript:void(0)" class="name">实验楼</a>
                    <div class="meta">
                        <span>关注 35</span>
                        <span>粉丝 8500</span>
                        <span>文章 100</span>
                    </div>
                    <div class="meta">
                        写了 10000 字，获得了 14775 个喜欢
                    </div>
                </div>
                <a href="javascript:void(0)" class="btn btn-default followers">
                    <i class="fa fa-check"></i>&nbsp;<span>已关注</span>
                </a>
            </li>
            <li>
                <a href="javascript:void(0)" class="avatar">
                    <img src="~/assets/img/my.gif" alt="">
                </a>
                <div class="info">
                    <a href="javascript:void(0)" class="name">实验楼</a>
                    <div class="meta">
                        <span>关注 35</span>
                        <span>粉丝 8500</span>
                        <span>文章 100</span>
                    </div>
                    <div class="meta">
                        写了 10000 字，获得了 14775 个喜欢
                    </div>
                </div>
                <a href="javascript:void(0)" class="btn btn-default followers">
                    <i class="fa fa-check"></i>&nbsp;<span>已关注</span>
                </a>
            </li>
            <li>
                <a href="javascript:void(0)" class="avatar">
                    <img src="~/assets/img/my.gif" alt="">
                </a>
                <div class="info">
                    <a href="javascript:void(0)" class="name">实验楼</a>
                    <div class="meta">
                        <span>关注 35</span>
                        <span>粉丝 8500</span>
                        <span>文章 100</span>
                    </div>
                    <div class="meta">
                        写了 10000 字，获得了 14775 个喜欢
                    </div>
                </div>
                <a href="javascript:void(0)" class="btn btn-default followers">
                    <i class="fa fa-check"></i>&nbsp;<span>已关注</span>
                </a>
            </li>
            <li>
                <a href="javascript:void(0)" class="avatar">
                    <img src="~/assets/img/my.gif" alt="">
                </a>
                <div class="info">
                    <a href="javascript:void(0)" class="name">实验楼</a>
                    <div class="meta">
                        <span>关注 35</span>
                        <span>粉丝 8500</span>
                        <span>文章 100</span>
                    </div>
                    <div class="meta">
                        写了 10000 字，获得了 14775 个喜欢
                    </div>
                </div>
                <a href="javascript:void(0)" class="btn btn-default followers">
                    <i class="fa fa-check"></i>&nbsp;<span>已关注</span>
                </a>
            </li>

        </ul>
    </div>
</template>
<script>
    export default{
        name:'Followers',
    }
</script>
<style scoped="">
    .following  .user-list .avatar{
        width: 52px;
        height: 52px;
        margin-right: 8px;
        vertical-align: middle;
        display: inline-block;
    }
    .following .user-list .avatar img{
        width: 100%;
        height: 100%;
        border: 1px solid #ddd;
        border-radius: 50%;
    }
    .following .user-list .info .name{
        font-size: 15px;
        font-weight: 700;
        color: #333;
    }
    .following .user-list .info .meta{
        padding-top: 2px;
        font-size: 12px;
        color: #969696;
    }
    .following .user-list .info .meta span{
        margin-right: 10px;
        padding-right: 10px;
        border-right: 1px solid #969696;
    }
    .following .user-list .info .meta span:last-child{
        border:none;
    }
    .followers{
        float: right;
        margin-top: 8px;
        padding: 8px 0;
        width: 100px;
        font-size: 15px;
        background-color: #fff;
        border-radius:40px;
        color: #969696 !important;
        border:1px solid #969696;
        box-shadow: none;
    }
</style>