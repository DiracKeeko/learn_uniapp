<template>
  <view class="out">
    <!-- 这里的key 如果是 index 勾选复选框，再删除，就会有问题 -->
    <checkbox-group @change="itemChange">
      <view v-for="(item, index) in productList" :key="item.id">
        <checkbox :value="item.id" :checked="item.checked"></checkbox>
        <text class="title">{{ item.name }}</text>
        <text class="price">{{ item.price }}</text>
        <text class="del" @click="handleDelete(index)">删除</text>
      </view>
    </checkbox-group>

    <view class="card">
      <view class="text"
        >选中{{ totalNumber }}个，总价：{{ totalPrice }}元</view
      >
    </view>

    {{ selectGroup }}
    <view>---</view>
  </view>
</template>

<script setup>
import { ref, computed } from "vue";
const productList = ref([
  { id: "11", name: "小米", price: 3999 },
  { id: "22", name: "华为", price: 8848 },
  { id: "33", name: "oppo", price: 4299 },
  { id: "44", name: "苹果", price: 8199 },
]);

const selectGroup = ref([]);
const totalNumber = computed(() => selectGroup.value.length);
const totalPrice = computed(() => {
  return productList.value
    .filter((item) => item.checked)
    .reduce((acc, cur) => acc + cur.price, 0);
});

function itemChange(e) {
  selectGroup.value = e.detail.value;
  productList.value.forEach((incomingData) => {
    incomingData.checked = selectGroup.value.includes(incomingData.id);
  });
}

function handleDelete(index) {
  productList.value.splice(index, 1);
}
</script>

<style lang="scss" scoped>
.out {
  .price {
    margin: 0 0 0 10px;
  }
  .del {
    margin: 0 0 0 15px;
    color: red;
  }
  .card {
    margin-top: 30px;
    border-top: 1px solid #eee;
    padding: 10px 0;
  }
}
</style>
