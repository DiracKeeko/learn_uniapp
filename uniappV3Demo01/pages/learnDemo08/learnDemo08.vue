<template>
  <view class="out">
    <input
      type="text"
      :value="inputValue"
      @focus="isActive = true"
      @blur="isActive = false"
    />
    <image
      src="../../static/chicken.gif"
      class="pic"
      :class="isActive ? 'active' : ''"
    />
  </view>
</template>

<script setup>
import { ref } from "vue";

const inputValue = ref("");
const isActive = ref(false);
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
