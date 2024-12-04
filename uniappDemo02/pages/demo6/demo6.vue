<template>
	<view>
		姓名: {{ name }}
	</view>
</template>

<script setup>
import { ref } from "vue";
import { onLoad } from "@dcloudio/uni-app";

const name = ref("Tom");
// onLoad(() => {
// 	console.log("onLoad");
// 	name.value = "Jerry"
// })

// onLoad的回调函数可以接收路由中的参数
onLoad((e) => {
	console.log("e->", e);
	name.value = e.name || "defaultName";
})	

</script>

<style>
	       
</style>
