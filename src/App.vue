<script>
export default {
  onLaunch: function () {
    console.log("App Launch", uni);
  },
  onShow: function () {
    console.log("App Show");
  },
  onHide: function () {
    console.log("App Hide");
  },
  onLoad() {
    console.log("页面启动的生命周期，这里编写页面加载时的逻辑");
    // 页面启动的生命周期，这里编写页面加载时的逻辑
  }
};
</script>

<style lang='scss'>
/*每个页面公共css */
@import "uview-plus/index.scss";
</style>
