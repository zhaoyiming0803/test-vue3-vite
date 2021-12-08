<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { ref } from 'vue'

import HelloWorld from './components/HelloWorld.vue'

// import { getAuthClient } from '@authing/native-js-ui-components'


import { AuthingGuard } from '@authing/vue-ui-components/src/components/index.js'
// import '@authing/vue-ui-components/lib/index.min.css'
// import { Test } from './components/Test/index.js'

// console.log('getAuthClient: ', getAuthClient)

const appId = ref('61ada53ae69e78d80e31d3e4')
const authingConfig = ref({
  apiHost: 'https://lb68p7-demo.authing.cn'
})

function onLogin (userInfo) {
  console.log('authing userInfo: ', userInfo)
}
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!--<Test></Test>-->
  <HelloWorld msg="Hello Vue 3 + Vite" />
  <AuthingGuard :appId="appId" @login="onLogin" :config="authingConfig" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
