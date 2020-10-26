<template>
    <div>
        <input type="text" v-model="msg">
        <button @click="add_note">添加留言</button>

        <ul>
            <li v-for="(note, index) in msg_list">
            <span>{{note}}</span> <a href="javascript:;" @click="delete_note(index)">删除</a>
            </li>
        </ul>
        <button v-show="isShow" @click="delete_all">删除全部</button>
    </div>
</template>

<script>
    export default {
        name: "Home",
        data: function () {
            return {
                msg: "",
                // 按段localStorage是否有值  有值则显示 如果没有 则设置成空数组
                isShow: localStorage.msgs ? true : false,
                msg_list: localStorage.msgs ? JSON.parse(localStorage.msgs) : [],

            }
        },
        methods: {
            add_note() {
                let msg = this.msg;
                if (msg) {
                    this.msg_list.push(this.msg);
                    // 将用户发表的留言储存到localstorage
                    // 储存前将数据进行序列化
                    localStorage.msgs = JSON.stringify(this.msg_list);
                    this.msg = "";
                    this.isShow = true
                }
            },
            delete_note(index) {
                this.msg_list.splice(index, 1)
                // let msg = localStorage.getItem("msgs")
                // localStorage.removeItem(msg(index))
                },

            delete_all() {
                localStorage.removeItem('msgs')
                this.msg_list = []
                this.isShow = false
            },
        }
    }
</script>

<style scoped>

</style>
