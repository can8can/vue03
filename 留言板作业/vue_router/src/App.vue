<template>
    <div id="app">
        <h3>教务管理</h3>
        <router-link to="/home">首页</router-link>
        <router-link to="/user">用户页</router-link>
        <hr>

        <router-view></router-view>

    </div>
</template>

<script>
    //import Home from "./components/Home";
    export default {
        name: 'App',
        components:{
        },
    }
</script>

<style>

</style>
