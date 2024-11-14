<template>
  <view class="">
    <view v-if="showJingDongStore">京东</view>
    <view v-else>淘宝</view>

    <view v-show="showJingDongStore">京东</view>
    <view v-show="!showJingDongStore">淘宝</view>
    <button type="primary" @click="changeStore">变更</button>

    <!-- template不会变为一个真实的dom元素 -->
    <template v-if="true">
      <view class="real-dom">真实的dom元素</view>
    </template>
  </view>
</template>

<script setup>
import { ref } from "vue";

const showJingDongStore = ref(true);

function changeStore() {
  showJingDongStore.value = !showJingDongStore.value;
  // console.log("showJingDongStore.value->", showJingDongStore.value);
}
</script>

<style lang="scss" scoped></style>
