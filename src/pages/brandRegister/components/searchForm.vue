<template>
  <div>
    <!-- -->

    <p>子组件内容如下</p>
    <view class="album">
      <view class="album__avatar">
        <image
          src="/static/brandAssess/qds-qrcode.jpg"
          mode=""
          style="width: 32px; height: 32px"
        ></image>
      </view>
      <view class="album__content">
        <up-text text="标题啊" type="primary" bold size="17"></up-text>
        <up-text margin="0 0 8px 0" text="全面的组件和便捷的工具会让您信手拈来，如鱼得水"></up-text>
        <up-album :urls="urls1" keyName="src2"></up-album>
      </view>
    </view>
    <view class="swiper">
      <u-swiper :list="props.imageList" @change="change" @click="imageClick"></u-swiper>
    </view>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { defineProps, reactive, defineEmits, watch } from "vue";

const props = defineProps({
  imageList: { type: Array, default: [] }
});

// 发射事件
const emit = defineEmits(["confirm", "update:showDialog"]);

const confirm = () => {};
const albumHeight = ref(0);
const urls1 = ref([
  {
    src2: "https://cdn.uviewui.com/uview/album/1.jpg"
  },
  ,
  {
    src2: "https://cdn.uviewui.com/uview/album/1.jpg"
  },
  { src2: "https://fanmingming.com/bing" }
]);

const change = () => {
  console.log("change", import.meta.env.VITE_FILE);
};

const imageClick = ind => {
  emit("confirm", "子组件被惦记了");
};
</script>

<style lang="scss" scoped>
.album {
  @include flex;
  align-items: flex-start;

  &__avatar {
    background-color: $u-bg-color;
    padding: 5px;
    border-radius: 3px;
  }

  &__content {
    margin-left: 10px;
    flex: 1;
  }
}
.swiper {
  display: block;
  width: 100%;
}
</style>