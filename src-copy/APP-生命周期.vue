<template>
    <div>
      <HelloWorld v-if="flag"></HelloWorld>
      <button @click="flag=!flag">销毁/创建</button>
    </div>
</template>

<script setup lang='ts'>
import { ref, reactive } from 'vue'
import HelloWorld from './components/A-生命周期.vue';

let flag = ref<Boolean>(true)
</script>

<style setup scoped>

</style>