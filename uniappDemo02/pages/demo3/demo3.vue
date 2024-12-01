<template>
	<view class="">
		<kk-child @add="handleAdd" @changeInput="handleInput"></kk-child>
		显示内容: {{ showText }}
	</view>
</template>

<script setup>
import { ref } from "vue";
const showText = ref(111);

function handleAdd(param) {
	console.log("param->", param);
	showText.value = param;
}

function handleInput(text) {
	showText.value = text;
}
</script>

<style lang="scss" scoped>
	       
</style>
