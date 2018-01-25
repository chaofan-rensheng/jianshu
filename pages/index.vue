<template>
    <div>
        <my-header></my-header>
        <b-container>
            <b-row>
                <b-col class="col-lg-9 bg-success">我占9个</b-col>
                <b-col class="col-lg-3 bg-info">我占3个</b-col>
            </b-row>
        </b-container>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        components:{
            myHeader
        }
    }
</script>