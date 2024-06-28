<template>
  <div class="person">
    <h2>姓名: {{ a }}</h2>
    <h2>年龄: {{ b }}</h2>
<!--    <button @click="changeName">修改名字</button>-->
<!--    <button @click="changeAge">修改年龄</button>-->
<!--    <button @click="showTel">显示电话</button>-->
  </div>
</template>

<script lang="ts">
export default {
  // 数据和方法
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Person',
  setup(){
    let name = '张三'
    let age = 14
    let tel = '13343434646'

    return {a:name,b:age,c:tel}
  },
}
</script>

<style >
  .person {
    background-color: green;
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
