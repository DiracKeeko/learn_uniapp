<template>
  <view class="">
    <kk-layout>
      <!-- 具名插槽 -->
      <template v-slot:header>demo1头部</template>
      <template #main> demo1内容区</template>
      <!-- # 是 v-slot: 的简写 -->
    </kk-layout>
  </view>
</template>

<script setup></script>

<style lang="scss" scoped></style>
