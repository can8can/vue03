<template>
    <div>
        <h4>用户详细信息展示</h4>
        这位同志的信息：<br>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
        ID：&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{{$route.params.id}}<br>
        姓名：&nbsp;&nbsp;{{$route.params.name}}<br>
        生日：&nbsp;&nbsp;{{$route.params.bir}}<br>
        内容：&nbsp;&nbsp;{{$route.params.con}}<br>
        <br>
        <button @click="goback">返回上一页</button>
    </div>

</template>

<script>
    export default {
        name: "UserDetail",
        methods:{
            goback(){
                this.$router.go(-1);
            },
        }
    }
</script>

<style scoped>

</style>
