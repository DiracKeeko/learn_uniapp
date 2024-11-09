<template>
  <view>
    <!-- size: default / mini -->
    <!-- type: primary / warn -->
    <button size="default" type="warn">按钮1</button>
    <button size="mini" type="primary">按钮2</button>
    <button size="default" type="primary" disabled="true">按钮3</button>
    <button size="default" type="primary" plain="true" disabled="true">
      按钮4
    </button>

    <!-- loading: true 视觉转圈，但是并未禁用 -->
    <button size="default" type="primary" loading="true">按钮5</button>
  </view>

  <view>-----</view>
  <view>
		<!-- 一般用placeholder-class 而不用placeholder-style -->
    <input type="text" placeholder="这是一个placeholder" placeholder-style="color: #ffeeaa" class="input-box" />
		<br>
		<text>↓ 手机拨号键盘</text>
		<!-- 手机上看才有效果 -->
    <input type="tel" class="input-box" />
		<br>
		<text>↓ 密码框</text>
		<input type="text" password="true" class="input-box" />
		<br>
		<text>↓ confirm-type</text>
		<!-- 手机上看才有效果 -->
		<input type="text" confirm-type="search" class="input-box" />
  </view>
</template>

<script setup></script>

<style>
.input-box {
  border: 1px solid #d9d9d9;
  border-radius: 4px;
}
</style>
