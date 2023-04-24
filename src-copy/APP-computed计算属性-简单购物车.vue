<template>
    <div>
      <table border style="width:500px">
        <thead>
          <tr>
            <th>商品</th>
            <th>数量</th>
            <th>单价</th>
            <th>操作</th>
          </tr>
        </thead>
  
        <tbody>
          <tr :key="item.id" v-for="(item,index) in data">
            <td>{{item.name}}</td>
            <td>
              <button @click="addAndSub(item,false)" style="backgroundColor:aliceblue">-</button>
              {{item.num}}
              <button @click="addAndSub(item,true)" style="backgroundColor:aliceblue">+</button>
            </td>
            <td>{{item.price}}</td>
            <td>
              <button @click="delItem(index)" style="backgroundColor:bisque">删除</button>
            </td>
          </tr>
        </tbody>
  
        <tfoot>
          <td></td>
          <td></td>
          <td></td>
          <td>总价：{{$total}}</td>
        </tfoot>
      </table>
    </div>
  
    <div>
      sbsbsbsbsbsbsbsbsb
    </div>
  </template>
  
  <script setup lang='ts'>
  import { reactive,computed } from 'vue'
  type Shop = {
    id:string,
    name: string,
    num: number,
    price: number
  }
  const data = reactive<Shop[]>([
    {
      id:'kuzi',
      name:'雨靴',
      num:1,
      price:100
    },
    {
      id:'yuyi',
      name:'雨衣',
      num:1,
      price:20
    },
    {
      id:'tietong',
      name:'铁桶',
      num:1,
      price:90
    }
  ])
  //计算属性就是响应式的不需要ref包裹
  //computed会缓存结果，不需要每个函数里面去调用
  let $total  = computed<number>(()=>{
    return data.reduce((prev,next)=>{
      return prev+(next.num*next.price)
    },0)
  })
  
  const addAndSub = (item:Shop, type:boolean)=>{
    if(item.num>1 && !type){
      item.num--
    }
    if(item.num<10 && type){
      item.num++
    }
  }
  
  const delItem = (index:number) => {
    data.splice(index,1)
  }
  
  
  
  </script>
  
  <style setup scoped>
  
  </style>