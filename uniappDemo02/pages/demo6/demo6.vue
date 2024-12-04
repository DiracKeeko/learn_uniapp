<template>
	<view>
		姓名: {{ name }}
	</view>
</template>

<script setup>
import { ref } from "vue";
import { onLoad } from "@dcloudio/uni-app";

const name = ref("Tom");
onLoad(() => {
	console.log("onLoad");
	name.value = "Jerry"
})
	
</script>

<style>
	       
</style>
