<template>
  <div class="Login2">
    <h1>Login2222</h1>
    <form>
      <div class="form-group">
        <label for="username">Username</label>
        <input type="text" id="username" v-model="username" required>
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <button type="submit" @click.prevent="login">Login</button>
    </form>
  </div>
</template>

<script lang="ts">
export default {
  // 数据和方法
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Login2',
}
</script>

<script lang="ts" setup>
import {ref} from 'vue'
let username = ref(0)
let password = ref(0)


function login(){
  // 登录逻辑
  console.log('Username:', username.value)
  console.log('Password:', password.value)
}

</script>


<style>
.login-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.5rem;
}

label {
  font-weight: bold;
}

input[type="text"],
input[type="password"] {
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1rem;
}

button[type="submit"] {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  background-color: #0074d9;
  color: #fff;
  cursor: pointer;
}

button[type="submit"]:hover {
  background-color: #0063aa;
}
</style>