<template>
    <div>
        <my-header></my-header>
        我是关注页面
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        name:'subscriptions',
        components:{
            myHeader
        }
    }
</script>