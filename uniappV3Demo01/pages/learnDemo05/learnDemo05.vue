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

  <br />
  <view class="box" :style="{ backgroundColor: bgColor }">box3</view>
  <button @click="changeBgColor">随机生成box3背景色</button>

	<br />
	<switch @change="switchChange" />
	<button type="primary" :loading="btnLoading">一个按钮</button>
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

const bgColor = ref("#bbffaa");
function changeBgColor() {
  const numberStr = Math.random().toFixed(6).slice(2);
  const colorStr = `#${numberStr}`;
  bgColor.value = colorStr;
}

const btnLoading = ref(false);
function switchChange(e) {
	console.log("e->", e);
	console.log(e.detail.value);
	btnLoading.value = e.detail.value;
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
