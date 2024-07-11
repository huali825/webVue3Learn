<!--log这里是界面布局 模板-->
<template>
  <div class="person">
  姓: <input type="text" v-model="NameLong.firstName"> <br>
  名: <input type="text" v-model="NameLong.lastName"> <br>
  全名: <span> ??-??</span> <br>
    <button @click ="addName">输出全名2</button>

  </div>
</template>


<script lang="ts">
export default {
  // 数据和方法
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Person',
}
</script>

<!--这里是变量和函数所在位置 脚本-->
<script lang="ts" setup>
  import {reactive} from 'vue'
  let NameLong = reactive({
    firstName: "zhang",
    lastName: "san",
    longName:""
  })

  function addName (name: string) {}



</script>


<!--log这里是控件的详细ui参数 样式-->
<style >
  .person {
    background-color: skyblue;
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

