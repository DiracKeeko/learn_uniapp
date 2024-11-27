<template>
	<view class="content">
		<UserInfo v-for="(item, index) in userList" :key="index" :userObj="item"></UserInfo>
		<UserInfo></UserInfo>
	</view>
</template>

<script setup>
import { ref } from "vue";
const userList = ref([
	{
		name: "张三",
		avatar: "../../static/pic1.jpg"
	},
	{
		name: "李四",
		avatar: "../../static/pic2.jpg"
	}
])
</script>

<style>
	
</style>
