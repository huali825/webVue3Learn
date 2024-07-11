<!--log这里是界面布局 模板-->
<template>
  <div class="person">
<!--    <button @click = "changeAge">修改年龄</button>-->
    <button @click = "addName">输出全名</button> <br>
  姓: <input type="text" v-model="NameLong.firstName"> <br>
  名: <input type="text" v-model="NameLong.lastName"> <br>
  全名: <span> {{name}}</span> <br>

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
import {reactive, ref} from 'vue'
  let name = ref("xxx")
  let NameLong = reactive({
    firstName: "zhang",
    lastName: "san",
    longName:""
  })

  function addName () {
    NameLong.longName = NameLong.firstName + NameLong.lastName
    name.value = NameLong.longName
  }



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

