<!--log这里是界面布局 模板-->
<template>
  <div class="Login">
    <button @click="login">登录</button>
    <h2>当前求和为: {{sum}}</h2>
    <button @click = "sumAndOne">数字加一</button>
  </div>
</template>


<script lang="ts">
export default {
  // 数据和方法
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Login',
}
</script>

<!--这里是变量和函数所在位置 脚本-->
<script lang="ts" setup>
import {ref} from 'vue'
  let sum = ref(0)
  function sumAndOne() {
    sum.value++
  }

  function login(){}

</script>


<!--log这里是控件的详细ui参数 样式-->
<style >
  .Login {
    background-color: white;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
  }
  button{
    width: 100px;
    height: 30px;
    line-height: 30px;
    text-align: center;
    margin: 5px;
  }

</style>

