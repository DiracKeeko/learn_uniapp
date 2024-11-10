<template>
  <view>
    <span>a:</span>
    {{ a }}
  </view>
  <view>
    <span>b:</span>
    {{ b }}
  </view>
  <view>
    <span>当前时间戳: </span>
    {{ Date.now() }}
  </view>
  <view>
    {{ fn() }}
  </view>
  <view>{{ showStr }}</view>
  <view>{{ showArr[1] }}</view>
  <view>{{ showObj.name }}</view>
  <button @click="changeValue">变更属性值</button>
</template>

<script setup>
import { ref } from "vue";

function fn() {
  return "在uni-app中学习vue3基础(组合式语法)";
}

// a 不是响应式
const a = 6;
// setInterval(() => {
//   a += 1;
//   console.log("a->", a); // a的值改变了，但是视图未更新
// }, 1000);

// b 是响应式，注意b是一个对象，需要手动变更b.value  
const b = ref(16); // 注意是用const 因为b是对象
console.log("b->", b); // b是一个对象
setInterval(() => {
  b.value += 1; // 变更b.value 而不是变更b
  // console.log("b.value->", b.value);
  // console.log("b->", b);
}, 1000);

const showStr = ref("showStr");
const showArr = ref([0, 1, 2]);
const showObj = ref({ name: "Mike" });

function changeValue() {
  // showArr.value[1] = "333"; // 通过arr[index]可以改变视图上的值
  showArr.value = [111, 222, 333]; // 直接变更整个数组也可以改变视图上的值 
  showObj.value.name = "Tom";
}
</script>

<style></style>
