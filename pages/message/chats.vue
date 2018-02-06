<template>
    <div>
        <my-header></my-header>
        <div>
            <div class="left">
                <nuxt-link to="/message/comments">评论</nuxt-link>
                <nuxt-link to="/message/chats">简信</nuxt-link>
            </div>
            <div class="right"></div>
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
        components:{
            myHeader,
        }
    }
</script>
<style>
    .left{
        width:35%;
        height:500px;
        background-color:red;
        float:left;
    }
    .right{
        width:60%;
        height:500px;
        background-color:green;
        display: inline-block;
        float:right;
    }
</style>