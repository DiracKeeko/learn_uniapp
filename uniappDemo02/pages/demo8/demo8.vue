<template>
  <view class="layout">
    <view class="box">这是box</view>
    <view class="text"> 欢迎使用 </view>
  </view>
</template>

<script setup></script>

<style lang="scss" scoped>
// video36 讲解通过PS改变设计稿尺寸，以及在线设计网站改变图像尺寸
.box {
  // width: 60%;
  // width: 40vw;
  // width: 400px;
  width: 375rpx; // rpx是响应式宽度的单位 在uniapp中 750rpx是100%宽度, 375rpx是50%宽度
  height: 130rpx;
  background: orange;
  font-size: 28rpx;
}
.text {
  font-size: 52rpx;
  // font-size: 52px;
  color: $custom-color-2;
}
</style>
