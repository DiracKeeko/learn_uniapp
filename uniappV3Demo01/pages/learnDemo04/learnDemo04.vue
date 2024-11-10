<template>
  <view>
    {{ a }}
  </view>
  <view>
    <span>当前时间戳: </span>
    {{ Date.now() }}
  </view>
  <view>
    {{ fn() }}
  </view>
</template>

<script setup>
const a = 6;
function fn() {
  return "在uni-app中学习vue3基础(组合式语法)";
}
</script>

<style></style>
