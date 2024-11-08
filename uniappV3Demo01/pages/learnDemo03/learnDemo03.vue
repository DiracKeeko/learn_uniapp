<template>
	<view>
		<!-- size: default / mini -->
		<!-- type: primary / warn -->
		<button size="default" type="warn">按钮1</button>
		<button size="mini" type="primary">按钮2</button>
		<button size="default" type="primary" disabled="true">按钮3</button>
		<button size="default" type="primary" plain="true" disabled="true">按钮4</button>
		
		<!-- loading: true 视觉转圈，但是并未禁用 -->
		<button size="default" type="primary" loading="true">按钮5</button>
	</view>
</template>

<script setup>
	
</script>

<style>
	       
</style>
