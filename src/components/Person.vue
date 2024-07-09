<template>
  <div class="person">
<!--    <h2>姓名: {{ name }}</h2>-->
<!--    <h2>年龄: {{ age }}</h2>-->
<!--    <h2>地址: {{ address }}</h2>-->
<!--    <button @click="changeName">修改名字</button>-->
<!--    <button @click="changeAge">修改年龄</button>-->
<!--    <button @click="showTel">显示电话</button>-->
    <h2>一辆{{car.brand}}车, 价值{{car.price}}万</h2>
    <button @click="changePrice">修改车辆价格</button>
    <button @click="changeBrand">修改汽车品牌</button>
    <button @click="changeCar">修改car obj</button>

    <br>
    <h2>游戏列表</h2>
    <ul>
      <li v-for="g in games" :key="g.gameId">{{g.gameName}}</li>
    </ul>
    <button @click="changeFirstGameName">改第一游戏名</button>

  </div>
</template>

<script lang="ts">
export default {
  // 数据和方法
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Person',
}
</script>

<script lang="ts" setup>
import {reactive, ref} from 'vue'

   let car = reactive({brand:'奔驰',price:20})
   let games = ref([
     {gameId: 1001,gameName:"王者荣耀"},
     {gameId: 1002,gameName:"原神"},
     {gameId: 1003,gameName:"绝区零"},
   ])

  function changePrice(){
    car.price += 10
  }
   function changeBrand(){
     car.brand = "奥迪"
   }
   function changeCar(){
     // car = {brand:'奥扩',price:3}
     // car = reactive({brand: "奥扩", price:4})

     Object.assign(car,{brand:"奥扩", price:5})
   }


  function changeFirstGameName(){
     games.value[0].gameName = "流星蝴蝶剑"
  }
</script>

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

