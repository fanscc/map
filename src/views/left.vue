<template>
  <div class="left_center">
    <div>
      <h4>社会服务 <img src="../assets/img/line1.gif" /></h4>
      <div class="left-top">
        <div class="swiper-container swiper2">
          <div class="swiper-wrapper">
            <div class="swiper-slide">
              <div v-for="item in 12" :key="item" class="item_tip">打卡</div>
            </div>
            <div class="swiper-slide">
              <div v-for="item in 12" :key="item" class="item_tip">扫描</div>
            </div>
          </div>
        </div>
        <span class="top-left-wiper2"></span>
        <span class="top-right-wiper2"></span>
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
      new Swiper(".left-top .swiper2", {
        navigation: {
          nextEl: ".top-left-wiper2",
          prevEl: ".top-right-wiper2"
        },
        autoplay: true,
        loop: false,
        observer: true,
        observeParents: true,
        disableOnInteraction: false,
        direction: "vertical",
        onSlideChangeEnd: function(swiper) {
          swiper.update(); //swiper更新
        },
        autoplayDisableOnInteraction: false
      });
    });
  }
};
</script>

<style lang="scss" scoped>
.left_center {
  width: 30%;
  .left-top {
    position: relative;
    padding: 0 50px;
    .top-left-wiper2,
    .top-right-wiper2 {
      position: absolute;
      top: 50%;
      display: inline-block;
      width: 18px;
      height: 45px;
      margin-top: -22.5px;
      outline: none;
      cursor: pointer;
    }
    .top-left-wiper2 {
      background: url(../assets/img/u122.png) no-repeat center;
      background-size: 100%;
      right: 4%;
    }
    .top-right-wiper2 {
      background: url(../assets/img/u123.png) no-repeat center;
      background-size: 100%;
      left: 4%;
    }
    .item_tip {
      display: flex;
      justify-content: space-between;
      height: 30px;
      line-height: 30px;
      box-sizing: border-box;
      margin-bottom: 5px;
      padding: 0 10px;
      cursor: pointer;
    }
    .item_tip:nth-of-type(odd) {
      background: rgba(24, 33, 106, 0.77);
    }
    .item_tip:nth-of-type(even) {
      background: rgba(59, 64, 136, 0.57);
    }
  }
}
</style>
