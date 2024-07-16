<!--log这里是界面布局 模板-->
<template>
  <div class="person">
    <h2>当前水温: {{temperature}}</h2>
    <h2>当前水位: {{height}}</h2>
    <button @click = "changeTemperature">数字加一</button>
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
import {ref, watchEffect} from 'vue'
  let temperature = ref(0)
  let height = ref(0)
  function changeTemperature() {
    temperature.value +=10
  }

  //全自动的监视
  watchEffect(() => {
    if (temperature.value >= 100) {
      temperature.value = 0
      console.log('给服务器发送请求')
    }
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

