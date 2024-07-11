<!--log这里是界面布局 模板-->
<template>
  <div class="person">
    <button @click = "addName">输出全名</button> <br>

    <button @click = "fullNameLisi">输出李四</button> <br>
  姓: <input type="text" v-model="NameLong.firstName"> <br>
  名: <input type="text" v-model="NameLong.lastName"> <br>
  全名变量按钮方式: <span> {{nameTemp}}</span> <br>

<!--    计算属性-->
  全名计算属性1: <span> {{fullName}}</span> <br>
    <br>
  <button @click = "changeFullName2">修改计算属性</button> <br>
  全名计算属性2: <span> {{fullName2}}</span> <br>

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
import {computed, reactive, ref} from 'vue'
  let nameTemp = ref("xxx")
  let NameLong = reactive({
    firstName: "zhang",
    lastName: "san",
    longName:""
  })

//  computed 计算属性的用法
// eslint-disable-next-line vue/return-in-computed-property
  let fullName = computed(() => {
    console.log(1)
    return NameLong.firstName.slice(0,1).toUpperCase() + NameLong.firstName.slice(1) + '_' + NameLong.lastName
  })

let fullName2 = computed({
  get(){
    return NameLong.firstName.slice(0,1).toUpperCase() + NameLong.firstName.slice(1) + '_' + NameLong.lastName
  },
  set(val){
    const [str1,str2] = val.split('_')
    NameLong.firstName = str1
    NameLong.lastName = str2
    //console.log(x)
    console.log('set', val)
  }
})

  function changeFullName2(){
    fullName2.value = 'li_si'
  }

  function addName () {
    NameLong.longName = NameLong.firstName  + '_' + NameLong.lastName
    nameTemp.value = NameLong.longName
  }

  function fullNameLisi () {
    nameTemp.value = "lisi"
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

