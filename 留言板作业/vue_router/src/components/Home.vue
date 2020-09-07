<template>
    <div>
        <h3>留言板</h3>
        <input type="text" v-model="msg">
        <button @click="add_note">发表</button>
        <br><br>

        留言内容：<br><br>
        <span v-for="(bb,index) in list">
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

        {{bb}}  <a href="javascript:;" @click="del(index)">删除</a><br>

    </span><br><br>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        <input type="button" value="全部删除" @click="del_all">
        <br><br>
        留言数：{{list.length}}
    </div>
</template>

<script>
    export default {
        name: "Home",
        data: function () {
            return {
                msg: "",
                list: localStorage.msgs ? JSON.parse(localStorage.msgs) : [],
            }
        },

    methods: {
           add_note(){
               let a=this.msg;
               if (a){
                   this.list.unshift(this.msg);
                   localStorage.msgs=JSON.stringify(this.list);
               }
               this.msg="";
           },
        del(a){
            localStorage.removeItem(this.list.splice(a,1))
            localStorage.msgs=JSON.stringify(this.list);
        },

        del_all(){
            localStorage.clear();
            this.list=[]
        },
        },
    }
</script>

<style scoped>

</style>
