<template>
  <view>
    <!-- swiper 轮播器 -->
    <!-- 指示点 indicator-dots, indicator-color + indicator-active-color -->
    <!-- 指示点 衔接 circular -->
    <!-- 自动播放 autoplay 自动切换时间间隔 interval 单位是ms -->
    <swiper
      indicator-dots="true"
      indicator-color="blue"
      indicator-active-color="#c020f0"
      circular="true"
      autoplay="true"
      interval="1500"
    >
      <swiper-item>111</swiper-item>
      <swiper-item>222</swiper-item>
      <swiper-item>333</swiper-item>
      <swiper-item>444</swiper-item>
    </swiper>

    <!-- vertical 纵向轮播，默认为false -->
    <swiper
      indicator-dots="true"
      vertical="true"
    >
      <swiper-item>111</swiper-item>
      <swiper-item>222</swiper-item>
      <swiper-item>333</swiper-item>
      <swiper-item>444</swiper-item>
    </swiper>

  </view>
</template>

<script setup></script>

<style lang="scss">
swiper {
  width: 90vw;
  height: 200px;
  margin: 0 auto;
  border: 1px solid green;
  swiper-item {
    width: 100%;
    height: 100%;
    background-color: pink;
  }
  swiper-item:nth-child(2n) {
    background-color: orange;
  }
}
</style>
