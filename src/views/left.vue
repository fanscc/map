<template>
  <div class="left_conten">
    <div>
      网关
    </div>
    <div class="left-tops">
      <div class="swiper-container swiper3">
        <div class="swiper-wrapper">
          <div class="swiper-slide">
            <h4>全国网关总数 <img src="../assets/img/line1.gif" /></h4>
            <p>100</p>
          </div>
          <div class="swiper-slide">
            <h4>全国节点总数 <img src="../assets/img/line1.gif" /></h4>
            <p>100</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper from "swiper";
export default {
  data() {
    return {};
  },
  mounted() {
    this.$nextTick(() => {
      new Swiper(".left-tops .swiper3", {
        autoplay: true,
        loop: false,
        autoplayDisableOnInteraction: false
      });
    });
  }
};
</script>

<style lang="scss" scoped>
.left_conten {
  width: 30%;
  color: #fff;
}
</style>
