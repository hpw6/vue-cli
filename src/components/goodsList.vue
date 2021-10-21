<template>
    <div name="show">
        <ul>
            <li v-for="good in list">
                <img v-bind:src="good.img">
                <p>{{good.goodName}}</p>
            </li>

        </ul>
    </div>
</template>

<script>
    export default {
        name: "show",
        data(){
            var obj = this;
            this.$http.get("json/dn.json").then(function (res) {
                obj.list=res.data;
            })
            return{
                list:[]
            }
        }
    }
</script>

<style scoped>

</style>
