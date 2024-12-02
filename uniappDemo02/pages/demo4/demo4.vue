<template>
  <view class="">
		<scroll-view :scroll-x="false" :scroll-y="true" class="scroll" ref="theScroll">
      <view>1111</view>
    </scroll-view>
		<life-demo v-if="show"></life-demo>
  </view>
</template>

<script setup>
// vue3中的mounted生命周期
import { ref, onMounted } from "vue";
const theScroll = ref(null); // 常量名和scroll-view中的ref名保持一致，在mounted周期内会自动绑定

console.log("setup-> scroll->", theScroll.value);

onMounted(()=>{
	console.log("onMounted-> scroll->", theScroll.value);
})

const show = ref(true);

setTimeout(()=>{
	show.value = false
},2000)

</script>

<style lang="scss" scoped></style>
