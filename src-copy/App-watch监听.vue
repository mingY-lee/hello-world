<template>
    <div>
        name: <input v-model="message.foo.bar.name">
        <br>
    </div>
  
    <div>
      sbsbsbsbsbsbsbsbsb
    </div>
  </template>
  
  <script setup lang='ts'>
  import { ref, reactive,computed, watch } from 'vue'
  
  let message = reactive({
    foo:{
      bar:{
        name:'hhh',
        age:24
      }
    }
  })
  // watch参数：
  //1. 所要监听的变量
    // 变量 / [变量1，变量2，...] / 回调函数
  //2. callback回调函数
  //3. 属性（reactive 变量为reactive就是深度监听）
  watch(()=>message.foo.bar.name,(newValue,oldValue)=>{
    console.log(newValue,oldValue)
  },{
    // deep:true,  //深度监听
    // immediate：true,  //立即执行callback
    //flush:"pre" //相对于组件更新前后何时去调用callback
    //pre组件更新前调用callback,sync同步，post更新后
  })
  
  
  
  </script>
  
  <style setup scoped>
  
  </style>