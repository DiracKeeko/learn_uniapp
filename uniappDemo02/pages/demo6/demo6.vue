<template>
  <view>
    姓名: {{ name }}
    <scroll-view ref="scroll"></scroll-view>
    <navigator url="/pages/demo5/demo5">跳转demo5</navigator>
    <view>-----</view>
    计数器: {{ count }}
  </view>
</template>

<script setup>
import { ref } from "vue";
import { onLoad, onReady, onShow, onHide } from "@dcloudio/uni-app";

const name = ref("Tom");
const scroll = ref(null);
const count = ref(0);

let timer;

// onLoad(() => {
// 	console.log("onLoad");
// 	name.value = "Jerry"
// })

// onLoad的回调函数可以接收路由中的参数
onLoad((e) => {
  console.log("e->", e);
  name.value = e.name || "defaultName";
  console.log("scroll in onLoad->", scroll?.value);
});

// onShow的第1种触发条件是加载页面的时候。
// onShow的第2种触发条件是在离开页面之后，返回回来的时候  (注意是返回回来的时候。如果是navigator跳转，则相当于重新加载)
// onShow的第3种触发条件是切换tab。离开tab再回来也会触发。
onShow(() => {
  console.log("onShow");
  timer = setInterval(() => {
    count.value += 1;
  }, 1000);
});

// onHide在 1.离开页面的时候  2.切换tab(离开当前tab)的时候触发
onHide(() => {
  console.log("onHide");
  clearInterval(timer);
});

// onLoad发生在页面初次渲染之前，因此无法获取dom元素
// 若想要获取dom元素，得用onReady生命周期
onReady(() => {
  console.log("scroll in onReady->", scroll?.value);
});

/* 
	执行顺序:
		1. onLoad
		2. onShow
		3. onReady
 
 */
</script>

<style></style>
