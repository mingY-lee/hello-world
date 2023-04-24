<template>
    <div>
      <h5>红红火火恍恍惚惚</h5>
      <hr>
      <div ref="div">{{ str }}</div>
      <button @click="onChange()">按钮</button>
    </div>
</template>

<script setup lang='ts'>
import { ref, reactive } from 'vue'
import { onBeforeMount,onMounted,onBeforeUpdate,onUpdated,onBeforeUnmount,onUnmounted } from 'vue'

//beforeCreate  created   
//setup语法糖模式是没有这两个生命周期的。 setup替代
console.log('setup：创建完成')

const str = ref<string>('金金')
const div = ref<HTMLDivElement>()

const onChange = ()=>{
  str.value = '鑫鑫'
}

//挂载
onBeforeMount(()=>{
  console.log('挂载之前=========》', div.value)
})
onMounted(()=>{
  console.log('挂载完成=========》', div.value)

})
//更新
onBeforeUpdate(()=>{
  console.log('更新之前=========》', div.value?.innerText)
})
onUpdated(()=>{
  console.log('更新完成=========》', div.value?.innerText)
})
//卸载
onBeforeUnmount(()=>{
  console.log('销毁之前=========》', div.value)
})
onUnmounted(()=>{
  console.log('销毁完成=========》', div.value)
})
</script>

<style setup scoped>

</style>