<template>
	<view>
		child子组件
		<button @click="$emit('add', 123)">123</button>
		<button @click="handleClick">456</button>
		<input type="text" @input="handleInput" />
	</view>
</template>

<script setup>
// 不同于 vue2 中 this.$emit(), 在vue3中需要先定义emit
// 定义 emit (vue3中 定义emit)
const emit = defineEmits(["add", "changeInput"]);

function handleClick() {
	emit("add", 456);
}

function handleInput(e) {
	emit("changeInput", e.detail.value);
}
</script>

<style lang="scss">

</style>