<!--log这里是界面布局 模板-->
<template>
  <div class="person">
    <h2>我的编号是: {{person.id}}</h2>
    <h2>我的名字是: {{person.name}}</h2>
    <h2>我的年龄是: {{person.age}}</h2>

    <h2>tempInt: {{tempInt}}</h2>
    <button @click = "addNum" >数字加一</button>
    <hr>
    <img v-for="(dog,index) in dogList" :src="dog" alt="">
    <hr>
    <button @click = "getDogImg" >再来个dog</button>
  </div>
</template>


<!--这里是变量和函数所在位置 脚本-->
<script lang="ts" setup name = "Person">
  import {type PersonInter} from '@/types'
  import {ref,reactive} from 'vue'
  import axios from 'axios'


  let person:PersonInter = {id:'10023455',name:'zhangSan', age:20};
  let tempInt = ref(0)
  let dogList = reactive([
    'https://images.dog.ceo/breeds/retriever-flatcoated/n02099267_882.jpg',
    'https://images.dog.ceo/breeds/dhole/n02115913_92.jpg',
    'https://images.dog.ceo/breeds/malamute/n02110063_4629.jpg'
  ])


  function addNum(){
    tempInt.value++
  }
  async function getDogImg() {
    let result = await axios.get('')
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
  img{
    width: 200px;
  }

</style>

