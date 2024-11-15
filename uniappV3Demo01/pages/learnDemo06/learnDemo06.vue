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
		
		<br />
		<view v-for="(item, index) in 5" :key="index">box {{ index }}</view>
		<!-- template 上写 v-for template也不会变为真实的dom元素 -->
    <!-- 
      vue 2.x 版本中在一个元素上同时使用 v-if 和 v-for 时，v-for 优先。
      vue 3.x 版本中在一个元素上同时使用 v-if 和 v-for 时，v-if 优先。
     -->
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
