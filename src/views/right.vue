<template>
  <div class="right_center">
    <div class="conten_video">
      <h4 style="font-size: 20px;">
        视频监控
        <div>
          <img src="../assets/img/line1.gif" />
        </div>
      </h4>
      <div>
        <video
          src="https://cdn-img.chiyue365.com/marketing/2019-0417.mp4"
          controls="controls"
          style="height: 100px;"
        >
          您的浏览器不支持 video 标签。
        </video>
      </div>
    </div>
    <div class="conten_renwu">
      <h4>
        任务
        <div>
          <img src="../assets/img/line1.gif" />
        </div>
      </h4>
      <div class="right-top">
        <div class="swiper-container swiper1">
          <div class="swiper-wrapper">
            <div class="swiper-slide">
              <div v-for="item in 6" :key="item" class="item_tip">打卡</div>
            </div>
            <div class="swiper-slide">
              <div v-for="item in 6" :key="item" class="item_tip">扫描</div>
            </div>
          </div>
        </div>
        <span class="top-left"></span>
        <span class="top-right"></span>
      </div>
    </div>
    <div class="conten_tip">
      <h4>
        告警
        <div>
          <img src="../assets/img/line1.gif" />
        </div>
      </h4>
      <div>
        <div class="right-top">
          <div class="swiper-container swiper1">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <div v-for="item in 6" :key="item" class="item_tip">高温</div>
              </div>
              <div class="swiper-slide">
                <div v-for="item in 6" :key="item" class="item_tip">缺水</div>
              </div>
            </div>
          </div>
          <span class="top-left"></span>
          <span class="top-right"></span>
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
      new Swiper(".right-top .swiper1", {
        navigation: {
          nextEl: ".top-left",
          prevEl: ".top-right"
        },
        autoplay: true,
        loop: false,
        observer: true,
        disableOnInteraction: false,
        observeParents: true,
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
.right_center {
  width: 25%;
  height: 100%;
  display: flex;
  flex-direction: column;
  .conten_renwu,
  .conten_tip {
    flex: 1;
    font-size: 20px;
  }
  .right-top {
    position: relative;
    padding: 0 50px;
    .top-left,
    .top-right {
      position: absolute;
      top: 50%;
      display: inline-block;
      width: 18px;
      height: 45px;
      margin-top: -22.5px;
      outline: none;
      cursor: pointer;
    }
    .top-left {
      background: url(../assets/img/u122.png) no-repeat center;
      background-size: 100%;
      right: 4%;
    }
    .top-right {
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
      font-size: 16px;
      cursor: pointer;
    }
    .item_tip:nth-of-type(odd) {
      background: rgba(24, 33, 106, 0.77);
    }
    .item_tip:nth-of-type(even) {
      background: rgba(59, 64, 136, 0.57);
    }
    .item_tip:hover {
      background: rgba(149, 146, 59, 0.5) !important;
    }
  }
}
</style>
