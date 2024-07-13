<template>
    <!--结构-->
    <div>
        <h1>tmhWechat </h1>
        <Login/>
      <br>
      <Login2/>
      <br>
        <Person/>
    </div>
</template>

<script lang=ts>
    //交互
    import Person from './components/Person.vue'
    import Login from "@/components/Login.vue";
    import Login2 from "@/components/Login2.vue";
    export default{
        name: 'App',
        components:{Login2, Login, Person}
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