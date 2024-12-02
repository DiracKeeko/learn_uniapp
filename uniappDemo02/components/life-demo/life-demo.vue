<template>
  <view> life-demo 组件 </view>
</template>

<script setup>
import { onUnmounted } from "vue";
onUnmounted(() => {
  console.log("onUnmounted -> 子组件被卸载了");
});
</script>

<style lang="scss" scoped></style>
