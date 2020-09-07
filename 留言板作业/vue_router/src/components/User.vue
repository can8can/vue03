<template>
    <div>
        <h3>用户列表</h3>
        <table border="2" >
            <tr>
                <td>ID</td>
                <td>姓名</td>
                <td>生日</td>
                <td>内容</td>
            </tr>
            <tr v-for="(user,index) in users" :key="user.id">
                <td>{{user.id}}</td>
                <td>{{user.username}}</td>
                <td>{{user.bir}}</td>
                <td>{{user.content}}</td>
                <td><a href="javascript:;" @click="del(index)">删除</a>|<router-link :to="`/detail/${user.id}/${user.username}/${user.bir}/${user.content}`">查看用户详情</router-link></td>
            </tr>
        </table>
        <button @click="goback">返回上一页</button>
    </div>
</template>

<script>
    export default {
        name: "User",
        data:function () {
            return {
                users:[
                    {id:1001,username:"张三",bir:"1999-01-02",content:"自我介绍"},
                    {id:1002,username:"李四",bir:"2009-03-04",content:"自我介绍"},
                    {id:1003,username:"王五",bir:"2019-05-06",content:"自我介绍"},
                ]
            }
        },
        methods:{
            del(index){
                console.log(index)
                this.users.splice(index,1)},
            goback(){
                this.$router.go(-1);
            },
        }

    }
</script>

<style scoped>
table{
    border-spacing: 0;
}
</style>
