<template>
  <div class="indicator-box">
    <div v-for="(item, index) in data" :key="index" class="single-indicator-box">
      <span class="indicator-title">{{item.name}}</span>
      <div class="indicator-content">
        <span class="hb">同比</span>
        <span class="sz">{{item.value1}}</span>
        <span class="hb-1">比年初</span>
        <span class="sz-1">{{item.value1}}</span>
        <!-- <span class="content-num">{{item.value2}}</span> -->
        <!-- <img class="hb-img" :src="imgYear[item.keyV]" alt /> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: ["ids", "chartData"],
  mounted() {
    // for (let i in this.ids) {
    //   this.initData(this.ids[i], this.chartData, i);
    //   this.initIndicator(this.ids[i], this.leftIndicator, i);
    // }
  },
  data() {
    return {
      data: [
        {
          name: "表内资产余额",
          value1: "24.3%",
          value2: 1234
        },
        {
          name: "表外资产余额",
          value1: "24.3%",
          value2: 1234
        }
      ],

      indData: {
        plan: 0,
        actual: 0
      },
      indicatorYear: {
        plan: 0,
        actual: 0
      },
      imgYear: {
        plan: null,
        actual: null
      }
    };
  },
  computed: {},
  methods: {
    // initData(id, chartData, index) {
    //   let temp = 0;
    //   if (this.currentPro === "全省") {
    //     temp = chartData
    //       ? chartData.y[index].data.reduce((pre, cur) => {
    //           return Number(pre) + Number(cur);
    //         })
    //       : 0;
    //     // } else if (this.currentPro === "直属单位") {
    //     //   let curIndex = chartData.x[0].data.indexOf("直属");
    //     //   temp = chartData ? chartData.y[index].data[curIndex] : 0;
    //   } else {
    //     let curIndex = chartData.x[0].data.indexOf(this.currentPro);
    //     temp = chartData ? chartData.y[index].data[curIndex] : 0;
    //   }
    //   this.indData[id.keyV] = temp;
    // },
    // // 初始化指标
    // initIndicator(id, data, index) {
    //   if (!data.x) return;
    //   let tempIncrement = 0,
    //     tempReduce = 0,
    //     tempPro = this.currentPro;
    //   if (this.currentPro === "全省") {
    //     tempPro = "合计";
    //   }
    //   let tempIndex = data.x[0].data.indexOf(tempPro);
    //   tempIncrement = data.y[0].data[tempIndex];
    //   tempReduce = data.y[1].data[tempIndex];
    //   this.indicatorYear["plan"] =
    //     (parseFloat(tempIncrement) * 100).toFixed(1) + "%";
    //   this.indicatorYear["actual"] =
    //     (parseFloat(tempReduce) * 100).toFixed(1) + "%";
    //   this.imgYear["plan"] = tempIncrement > 0 ? UPImg : DOWNImg;
    //   this.imgYear["actual"] = tempReduce > 0 ? UPImg : DOWNImg;
    // }
  },
  components: {},
  watch: {
    chartData: function(newVal) {
      //   for (let i in this.ids) {
      //     this.initData(this.ids[i], newVal, i);
      //     this.initIndicator(this.ids[i], this.leftIndicator, i);
      //   }
    }
  }
};
</script>

<style lang="less" scoped>
.single-indicator-box {
  width: 100%;
  height: 166px;
  margin-bottom: 30px;
  background: url("../../assets/images/jinchukou/Frame-824@1x.png") no-repeat;
  background-size: 100% 100%;
  // margin: 0 12px;
  padding: 0 10px;
  display: inline-block;
  .indicator-title {
    display: block;
    height: 60px;
    line-height: 60px;
    opacity: 0.699999988079071;
    color: rgba(255, 255, 255, 1);
    font-family: Microsoft YaHei;
    font-weight: bold;
    font-size: 14px;
    letter-spacing: 0px;
    text-align: left;
    padding-left: 20px;
  }
  .indicator-content {
    height: 95px;
    position: relative;
    color: rgba(255, 255, 255, 1);
    font-family: PingFang SC;
    font-weight: medium;
    font-size: 28px;
    text-align: left;

    .content-num,
    .content-rate {
      display: inline-block;
    }
    .content-num {
      color: rgba(255, 179, 88, 1);
      font-size: 24px;
      padding-left: 20px;
      font-family: Google Sans;
      .content-unit {
        font-size: 28px;
      }
    }
    .hb {
      position: absolute;
      left: 20px;
      width: 80px;
      top: 10px;
      font-size: 14px;
      color: rgba(255, 255, 255, 0.6);
    }
    .sz {
      position: absolute;
      left: 20px;
      width: 80px;
      top: 45px;
      font-size: 28px;
    }
    .hb-1 {
      position: absolute;
      right: 20px;
      width: 120px;
      top: 10px;
      font-size: 14px;
      color: rgba(255, 255, 255, 0.6);
    }
    .sz-1 {
      position: absolute;
      right: 20px;
      width: 120px;
      top: 45px;
      font-size: 28px;
    }
    .hb-img {
      position: absolute;
      right: -1px;
      top: 59px;
      font-size: 28px;
    }
  }
}
</style>
