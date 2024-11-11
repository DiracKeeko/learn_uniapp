<template>
	<view>
		<image :src="picUrl"></image>
	</view>
</template>

<script setup>
	import {ref } from "vue";
	
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
	}, 1600)
	
</script>

<style>
	       
</style>
