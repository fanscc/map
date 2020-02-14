<template>
  <div class="home_center">
    <div id="leftTop" style="width: 100%;height: 300px;"></div>
  </div>
</template>

<script>
let options = {
  title: {
    text: "华南地区网关数量统计",
    textStyle: {
      color: "#fff"
    }
  },
  tooltip: {
    trigger: "axis",
    axisPointer: {
      type: "shadow"
    }
  },
  legend: {
    data: ["网关"],
    textStyle: {
      color: "#fff"
    }
  },
  grid: {
    left: "3%",
    right: "4%",
    bottom: "3%",
    containLabel: true
  },
  xAxis: {
    type: "value",
    boundaryGap: [0, 0.01],
    axisLabel: {
      textStyle: {
        color: "#7edae8" //坐标的字体颜色
      }
    }
  },
  yAxis: {
    type: "category",
    data: ["桂林市", "清远市", "广州市", "湛江市"],
    axisLabel: {
      textStyle: {
        color: "#7edae8" //坐标的字体颜色
      }
    }
  },
  series: [
    {
      name: "网关",
      type: "bar",
      data: [13, 32, 22, 6],
      itemStyle: {
        normal: {
          color: "yellow"
        }
      }
    }
  ]
};
export default {
  data() {
    return {
      chartInstance: null
    };
  },
  created() {
    this.$nextTick(() => {
      this.chartInstance = this.$echarts.init(
        document.getElementById("leftTop")
      );
      this.chartInstance.setOption(options);
    });
  },
  methods: {}
};
</script>
