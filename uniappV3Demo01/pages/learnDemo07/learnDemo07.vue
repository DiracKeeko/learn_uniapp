<template>
  <view class="out">
    <!-- 这里的key 如果是 index 勾选复选框，再删除，就会有问题 -->
    <view v-for="(item, index) in productList" :key="item.id">
      <checkbox></checkbox>
      <text class="title">{{ item.name }}</text>
      <text class="del" @click="handleDelete(index)">删除</text>
    </view>
  </view>
</template>

<script setup>
import { ref } from "vue";
const productList = ref([
  { id: 11, name: "小米" },
  { id: 22, name: "华为" },
  { id: 33, name: "oppo" },
  { id: 44, name: "苹果" },
]);

function handleDelete(index) {
  productList.value.splice(index, 1);
}
</script>

<style lang="scss" scoped>
.out {
  .del {
    margin: 0 0 0 15px;
    color: red;
  }
}
</style>
