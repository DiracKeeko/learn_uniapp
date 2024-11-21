<template>
  <view class="out">
    <input type="text" v-model="firstName" placeholder="firstName" />
    <input type="text" v-model="lastName" placeholder="lastName" />
    fullName: {{ fullName }}

    <view>--------</view>
    <input type="text" v-model="person.name" placeholder="person" />
    全称：{{ person }}
  </view>
</template>

<script setup>
import { ref, watch, watchEffect } from "vue";
const firstName = ref("first");
const lastName = ref("last");
const fullName = ref("first last");

const person = ref({
  name: "Tom",
  age: 5,
});

// watch([firstName, lastName], ([newF, newL], [oldF, oldL]) => {
//   fullName.value = newF + " " + newL;
// });

// watchEffect 监听所有ref定义的数据源的改变
watchEffect(() => {
  fullName.value = firstName.value + " " + lastName.value;
  console.log("watchEffect->", { firstName, lastName, person });
});

// watch监听的是一个ref创建的变量 (是firstName, 不是firstName.value)
// 默认是浅监听
watch(firstName, (newVal, oldVal) => {
  console.log("newVal->", newVal);
  console.log("oldVal->", oldVal);
});

// 浅监听 -> input 改变person.value 下面的监听不触发
watch(person, (newVal, oldVal) => {
  console.log("newVal->", newVal);
  console.log("oldVal->", oldVal);
});
// 传入函数 用来监听对象中的某个属性 (本质上还是浅监听)
watch(
  () => person.value.name,
  (newVal, oldVal) => {
    console.log("监听对象的某个key");
    console.log("newVal->", newVal);
    console.log("oldVal->", oldVal);
  }
);

// 深监听 (监听整个对象的变更) 开启{deep: true} 同理还有 immediate
watch(
  person,
  (newVal, oldVal) => {
    console.log("深监听");
    console.log("newVal->", newVal);
    console.log("oldVal->", oldVal);
  },
  { deep: true, immediate: true }
);
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
