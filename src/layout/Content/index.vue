<template>
    <div class="content">
        <div class="content-items" v-for="item in 100">{{item}}</div>
    </div>
</template>

<script setup lang='ts'>
// import { ref, reactive } from 'vue'

</script>

<style lang="less" setup scoped>
.content {
    height:100%;
    flex:1;
    margin: 20px;
    border: 1px solid #ccc;
    overflow: auto;
    // &-items {
    //     padding:20px;
    //     border: 1px solid #ccc
    // }
}
</style>