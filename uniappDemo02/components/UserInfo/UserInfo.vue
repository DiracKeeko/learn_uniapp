<template>
  <view class="user-info">
    <image :src="avatar" mode="" class="avatar"></image>
    <view>{{ handleName(username) }}</view>
  </view>
</template>

<script setup>
const props = defineProps(["username", "avatar"])
/* 
// 如果需要控制台打印，或者是处理username等传入参数的内容，则需要用变量接住这个props  
// const props = defineProps([...])
const props = defineProps(["username", "avatar"])
console.log("username->", props.username);
*/

// ↓ 执行失败，username没有变化。 因为props是单向数据源，只读。
// props.username += "@"; // Set operation on key "username" failed: target is readonly
// 如果想对username做处理，可以用computed，也可以用function
function handleName(name) {
  return name + "@";
}

</script>

<style lang="scss" scoped>
.user-info {
  width: 100%;
  height: 200px;
  background: #ccc;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  image {
    width: 100px;
    height: 100px;
    border-radius: 50%;
  }
  .username {
    padding: 10px 0;
    font-size: 20px;
  }
}
</style>
