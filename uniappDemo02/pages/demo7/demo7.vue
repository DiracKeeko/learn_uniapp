<template>
  <view class=""> 生命周期 </view>
  <navigator url="/pages/demo6/demo6">点击跳转demo6</navigator>
  <navigator open-type="reLaunch" url="/pages/demo4/demo4">跳转demo4销毁当前页</navigator>
</template>

<script setup>
import { onBeforeMount, onMounted, ref } from "vue";
import {
  onLoad,
  onReady,
  onShow,
  onHide,
  onUnload,
} from "@dcloudio/uni-app";

const count = ref(0);
const fixed = ref(false);

onLoad((e) => {
  console.log("onload函数");
});

onShow(() => {
  console.log("onShow函数");
});

onHide(() => {
  console.log("onHide函数");
});

onReady((e) => {
  console.log("onReady函数");
});

onBeforeMount(() => {
  console.log("onBeforeMount函数");
});

onMounted(() => {
  console.log("onMounted函数");
});

onUnload(() => {
  console.log("onUnload卸载页面");
});

/* 
  App Launch
  App Show
  onload函数
  onShow函数
  onBeforeMount函数
  onReady函数
  onMounted函数

  // 离开
  onHide函数

  // 销毁当前页
  onUnload卸载页面
 */
</script>

<style lang="scss" scoped>
.fixed {
  width: 100px;
  height: 100px;
  background: orange;
  position: fixed;
  right: 30px;
  bottom: 30px;
}
</style>
