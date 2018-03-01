<template>
    <div>
        <my-header></my-header>
        <div class="my-container new-collection">
            <div class="row">
                <div class="col-9" style="margin-left:150px;padding-top:30px;">
                    <h3>新建专题</h3>
                    <table>
                        <thead></thead>
                        <tbody class="base">
                            <tr>
                                <td style="width:150px;">
                                    <div class="avatar-collection">
                                        <img src="../../static/avatar-collection.png" alt="">
                                    </div>
                                </td>
                                <td style="width:540px;">
                                    <a href="javascript:void(0)" class="upload">
                                        上传专题封面
                                    </a>
                                </td>
                            </tr>
                            <tr>
                                <td  class="setting-title">名称</td>
                                <td>
                                    <input type="text" placeholder="填写名称，不超过50字">
                                </td>
                            </tr>
                            <tr>
                                <td class="setting-title">描述</td>
                                <td>
                                    <textarea placeholder="填写描述"></textarea>
                                </td>
                            </tr>
                            <tr>
                                <td  class="setting-title">其他管理员</td>
                                <td>
                                    <input type="text" placeholder="输入用户名">
                                </td>
                            </tr>
                            <tr>
                                <td  class="setting-title">是否允许投稿</td>
                                <td>
                                    <div style="width:200px;"><input type="radio" class="radio" name="push" checked @click="dis=false;disClass=false"><span>允许</span></div>
                                    <div><input type="radio" class="radio" name="push" @click="dis=true;disClass=true"><span>不允许</span></div>
                                </td>
                            </tr>
                            <tr :class="{disable:disClass}">
                                <td  class="setting-title" :class="{disable:disClass}">投稿是否需要审核</td>
                                <td>
                                    <div style="width:200px;"><input  type="radio" class="radio" name="verify" :disabled="dis" checked><span>需要</span></div>
                                    <div><input type="radio" class="radio" name="verify" :disabled="dis"><span>不需要</span></div>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                    <div class="create">创建专题</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        data(){
            return{
                dis:false,
                disClass:false
            }
        },
        components:{
            myHeader
        },
        methods:{
            unallow(){
                console.log(this.$refs.radio)
            }
        }
    }
</script>
