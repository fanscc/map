<template>
  <div class="map_big">
    <div class="nav_conten">
      <div>2020-01-11 18:00</div>
      <div>华山众创智慧农业</div>
      <div>logo</div>
    </div>
    <div style="display: flex">
      <map_left></map_left>
      <map_center></map_center>
      <map_right></map_right>
    </div>
  </div>
</template>

<script>
import map_center from "@/views/Home.vue";
import map_left from "@/views/left.vue";
import map_right from "@/views/right.vue";
export default {
  data() {
    return {};
  },
  components: {
    map_left,
    map_center,
    map_right
  }
};
</script>

<style lang="scss" scoped>
.map_big {
  height: 100%;
  background: url(../assets/img/bg.png) no-repeat center;
  background-size: 100% 100%;
  color: #fff;
  .nav_conten {
    display: flex;
    height: 50px;
    line-height: 50px;
    font-weight: 900;
    & > div {
      text-align: center;
      line-height: 50px;
    }
    div:nth-of-type(1) {
      width: 30%;
    }
    div:nth-of-type(2) {
      width: 40%;
    }
    div:nth-of-type(3) {
      width: 30%;
    }
  }
}
</style>
