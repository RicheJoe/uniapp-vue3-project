<template>
  <view class="content">
    <div class="text-area" v-for="item in list" :key="item.text">
      <up-button type="primary" :text="item.text" @click="goPath()" />
    </div>
  </view>
</template>

<script setup>
import { ref } from "vue";
const list = ref([
  {
    text: "点赞",
    color: "blue",
    fontSize: 28
  },
  {
    text: "分享"
  },
  {
    text: "评论"
  }
]);

const show = ref(true);

function goPath() {
  uni.navigateTo({
    url: "/pages/brandRegister/index"
  });
}
// export default {
//   data() {
//     return {
//       title: "Hello"
//     };
//   },
//   onLoad() {},
//   methods: {}
// };
</script>

<style lang='scss'>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-image: url("/static/brandAssess/list-header.png");
}
</style>
