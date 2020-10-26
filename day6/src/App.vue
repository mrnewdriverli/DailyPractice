<template>
    <div id="app">

        <h3>这是主页</h3>
        <router-link to="/home">留言板</router-link>
        <router-link to="/user">用户信息</router-link>
        <hr>

        <!--    组件对应内容的显示地址    -->
        <router-view></router-view>
    </div>
</template>

<script>
export default {
    name: 'App'
}
</script>

<style>

</style>
