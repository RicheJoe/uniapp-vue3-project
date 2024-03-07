<template>
  <div>
    <!-- 商标注册-->
    <u-search
      placeholder="日照香炉生紫烟"
      v-model="keyword"
      :clearabled="true"
      @search="inputChange"
    ></u-search>

    <childSearch :imageList="imageList" @confirm="imageClick" />
  </div>
</template>

<script setup>
import { ref, watch, onMounted, onBeforeMount } from "vue";
import childSearch from "@/pages/brandRegister/components/searchForm.vue";
import { onLoad, onReady } from "@dcloudio/uni-app";

const keyword = ref("遥看瀑布挂前川");
const imageList = ref([
  "https://cdn.uviewui.com/uview/swiper/swiper1.png",
  "https://cdn.uviewui.com/uview/swiper/swiper2.png",
  "https://cdn.uviewui.com/uview/swiper/swiper3.png"
]);
const inputChange = val => {
  console.log(val);
};
const imageClick = val => {
  console.log(val, keyword.value);
};

watch(keyword, n => {
  console.log("watch", n);
});
onBeforeMount(() => {
  console.log("onBeforeMount");
});
onMounted(() => {
  console.log("onMounted");
});
onLoad(() => {
  console.log("onLoadonLoadonLoadonLoadonLoadonLoadonLoadonLoad");
});
onReady(() => {
  console.log("onReadyonReadyonReadyonReadyonReadyonReady");
});
</script>

<style lang="scss" scoped>
</style>