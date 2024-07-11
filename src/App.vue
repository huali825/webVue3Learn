<template>
    <!--结构-->
    <div>
        <h1>今天才看了多少赶紧看看你的 </h1>
        <Person/>
        <Person/>
        <Person/>
    </div>
</template>

<script lang=ts>
    //交互
     import Person from './components/Person.vue'
    export default{
        name: 'App',
        components:{Person}
    }
</script>

<style scoped>
    /* 样式 */
    .app{
        background-color: red;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 40px;
    }
</style>