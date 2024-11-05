<template>
	<view class="box" hover-class="box-hover" hover-start-time="10" hover-stay-time="50">
		view布局标签
		<view class="inner" hover-class="inner-hover" hover-stop-propagation>内部元素</view>
	</view>

	<view>view标签中的文字不能复制</view>

	<view>---------</view>

	<text selectable>text标签+文本可选</text>

	<br>
	<text space="nbsp">text标签 连续空格</text>
	<br>
	<text space="ensp">text标签 连续空格</text>
	<br>
	<text space="emsp">text标签 连续空格</text>

	<br>
	<scroll-view scroll-y="true" scroll-x class="first-scroll-view">
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
		<view class="inner-box">scroll的子元素</view>
	</scroll-view>
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

	.first-scroll-view {
		width: 50%;
		height: 200px;
		border: 1px solid red;
		.inner-box {
			width: 600px;
			height: 50px;
			border: 1px solid blue;
		}
	}
</style>