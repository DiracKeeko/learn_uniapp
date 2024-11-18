<template>
  <view class="out">
    <!-- confirm事件在 pc端按下enter, 移动端按下小键盘确定 的时机 触发 -->
    <input
      type="text"
      @focus="isActive = true"
      @blur="isActive = false"
      :value="inputValue"
      @input="(e) => (inputValue = e.detail.value)"
      @confirm="handleConfirm"
    />

    <!-- 上面的 :value + @input 等价于下面的v-model -->
    <!-- <input
		  type="text"
		  @focus="isActive = true"
		  @blur="isActive = false"
		  v-model="inputValue"
		/> -->

    <image
      src="../../static/chicken.gif"
      class="pic"
      :class="isActive ? 'active' : ''"
    />
    预览：{{ inputValue }}
  </view>
</template>

<script setup>
import { ref } from "vue";

const inputValue = ref("");
const isActive = ref(false);

// 将handleInput写在html代码块中
// function handleInput(e) {
// 	// console.log(e);
// 	inputValue.value = e.detail.value; // 注意这里是 e.detail.value 不是 e.target.value
// }

function handleConfirm(e) {
  console.log(e);
}
</script>

<style lang="scss" scoped>
.out {
  position: relative;
  padding: 0 20px;
  margin: 40px 0 0 0;
  input {
    border: 1px solid #ccc;
    height: 40px;
    background: #fff;
    position: relative;
    z-index: 2;
  }

  .pic {
    width: 24px;
    height: 24px;
    position: absolute;
    z-index: 1;
    top: 0;
    left: 50%;
    transition: top 0.3s;
  }

  .pic.active {
    top: -24px;
  }
}
</style>
