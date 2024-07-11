<!--log这里是界面布局 模板-->
<template>
  <div class="person">
    <h2>姓名: {{name}}</h2>
    <h2>年龄: {{person.age }}</h2>
    <button @click = "changeName">修改名字</button>
    <button @click = "changeAge">修改年龄</button>
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
  import {reactive,toRefs} from 'vue'
  let person = reactive({
    name: "张三",
    age: 5,
  })

  let {name,age} = toRefs(person)

  function changeName() {
    person.name = "李四"
    name.value = "王五"
  }
  function changeAge() {
    age.value = 7
    person.age = 6
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

