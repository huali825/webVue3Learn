<!--log这里是界面布局 模板-->
<template>
  <div class="person">
  <h2>我的编号是: {{person.id}}</h2>
  <h2>我的名字是: {{person.name}}</h2>
  <h2>我的年龄是: {{person.age}}</h2>

  <h2>tempInt: {{tempInt}}</h2>

  </div>
</template>


<!--这里是变量和函数所在位置 脚本-->
<script lang="ts" setup name = "Person">
  import {type PersonInter} from '@/types'
  let person:PersonInter = {id:'10023455',name:'zhangSan', age:20};

  import {ref,onBeforeMount,onMounted,onBeforeUpdate,onUpdated} from 'vue'
  let tempInt = ref(0)
  console.log("创建了")
  onBeforeMount(()=>{
    console.log("挂载前")
  })
  onMounted(()=>{
    console.log("挂载完毕")
  })
  onBeforeUpdate(()=>{
    console.log("更新前")
  })
  onUpdated(()=>{
    console.log("更新完毕")
  })


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

