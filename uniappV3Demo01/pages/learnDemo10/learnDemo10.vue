<template>
  <view class="out">
    firstName: <input type="text" v-model="firstName" /> lastName:
    <input type="text" v-model="lastName" />
    <br />
    <view>-------</view>
    fullName: {{ firstName }}-{{ lastName }}
    <br />
    <br />
    <view>-------</view>
    fullName computed: {{ fullName }}
  </view>
</template>

<script setup>
import { ref, computed } from "vue";
const firstName = ref("");
const lastName = ref("");

const fullName = computed(() => `${firstName.value}-${lastName.value}`);

// script中使用 computed的值 也需要.value
// console.log(fullName.value);
</script>

<style lang="scss" scoped>
.out {
  padding: 20px;

  input {
    border: 1px solid #ccc;
    height: 40px;
    padding: 0 10px;
    margin: 10px 0;
  }
}
</style>
