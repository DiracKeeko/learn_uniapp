<template>
  <view class="out"> 子组件count值：{{ count }} </view>
</template>

<script setup>
import { ref } from "vue";
const count = ref(100);
const updateCount = function () {
  count.value++;
};

// defineExpose 向外暴露组件的属性和方法
defineExpose({
  count,
  str: "hello",
  updateCount,
});
</script>

<style lang="scss" scoped>
.out {
  padding: 20px;
  background: #eee;
}
</style>
