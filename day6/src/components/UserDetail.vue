<template>
    <div>
        用户详细信息:<br>
        序号：{{$route.params.id }}<br>
        姓名：{{$route.params.username }}<br>
        生日：{{$route.params.bir }}<br>
        简介：{{$route.params.content }}<br>
    </div>
</template>

<script>
export default {
    name: "UserDetail",
}
</script>

<style scoped>

</style>
