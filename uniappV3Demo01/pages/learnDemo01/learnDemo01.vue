<template>
	<view class="box" hover-class="box-hover" hover-start-time="10" hover-stay-time="50">
		view布局标签
		<view class="inner" hover-class="inner-hover" hover-stop-propagation>内部元素</view>
	</view>
</template>

<script setup>

</script>

<style>
	.box {
		width: 200px;
		height: 200px;
		background-color: #ccc;
	}

	.inner {
		width: 150px;
		height: 150px;
		background-color: green;
	}

	.box-hover {
		width: 300px;
		background-color: orange;
	}

	.inner-hover {
		background-color: greenyellow;
	}
</style>