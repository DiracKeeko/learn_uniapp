<template>
	<view>
		姓名: {{ name }}
		<scroll-view ref="scroll"></scroll-view>
	</view>
</template>

<script setup>
import { ref } from "vue";
import { onLoad, onReady } from "@dcloudio/uni-app";

const name = ref("Tom");
const scroll = ref(null);

// onLoad(() => {
// 	console.log("onLoad");
// 	name.value = "Jerry"
// })

// onLoad的回调函数可以接收路由中的参数
onLoad((e) => {
	console.log("e->", e);
	name.value = e.name || "defaultName";
	console.log("scroll in onLoad->", scroll?.value);
})	

// onLoad发生在页面初次渲染之前，因此无法获取dom元素
// 若想要获取dom元素，得用onReady生命周期
onReady(() => {
	console.log("scroll in onReady->", scroll?.value);
})
</script>

<style>
	       
</style>
