<template>
  <view>
    <image :src="picUrl"></image>
  </view>
  <br />
  <view class="box" :class="{ active: isActive }"></view>
  <br />
  <view class="box" :class="isActive ? 'active' : ''"></view>
  <br />
  <button @click="toggleActive">切换激活状态</button>
</template>

<script setup>
import { ref } from "vue";

const urlArr = [
  "../../static/pic1.png",
  "../../static/pic2.png",
  "../../static/pic4.jpg",
];

const picUrl = ref(urlArr[0]);

let i = 0;
setInterval(() => {
  const len = urlArr.length;
  i += 1;
  picUrl.value = urlArr[i % len];
}, 1600);

const isActive = ref(true);
function toggleActive() {
  isActive.value = !isActive.value;
}
</script>

<style lang="scss">
.box {
  width: 200px;
  height: 200px;
  background-color: orange;
}

.active {
  background-color: lightblue;
}
</style>
