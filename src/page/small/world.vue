<template>
  <div class="container">
    <!-- 头部 -->
    <div class="title-frame">
      <div class="title-left"></div>
      <div class="global-title">中国进出口银行</div>
      <div class="right-time"></div>
    </div>
    <!-- <world-chart class="world-chart" /> -->
    <left-indicator class="left-indicator" />
  </div>
</template>

<script>
import Vue from "vue";
import WorldChart from "@/components/world/worldChart.vue";
import LeftIndicator from "@/components/world/leftIndicator.vue";

export default {
  mounted() {},
  data() {
    return {};
  },
  computed: {},
  methods: {},
  beforeDestroy() {},
  components: {
    WorldChart,
    LeftIndicator
  }
};
</script>

<style lang="less" scoped>
.container {
  width: 3840px;
  height: 2160px;
  
  background: url("../../assets/images/jinchukou/bg@1x.png") no-repeat;
  background-size: 100% 100%;
  font-size: 28px;
  color: #fff;
  overflow: hidden;
  font-family: Microsoft YaHei;

  // 标题样式
  .title-frame {
    width: 100%;
    height: 7%;
    background: url("../../assets/images/home/header.png") no-repeat;
    background-size: 100% 100%;
    display: flex;
    justify-content: space-between;
    padding: 0 1%;
    .title-left {
      width: 33%;
    }
    .global-title {
      text-align: center;
      width: 33%;
      padding-top: 24px;
      font-size: 64px;
      font-weight: bold;
      font-family: FZZhengHeiS-B-GB;
    }
    .right-time {
      width: 33%;
      text-align: right;
    }
  }

  .world-chart {
    position: absolute;
    left: 0;
    top: 151px;
    height: 2000px;
    width: 100%;
  }

  .left-indicator {
    position: absolute;
    left: 66px;
    top: 1312px;
    width: 652px;
    height: 748px;
  }

  //   // 内容样式
  //   .frame-content {
  //     display: flex;
  //     justify-content: space-between;
  //     .accruing-amounts,
  //     .accruing-person {
  //       width: 28%;
  //       height: 92.96%;
  //       padding: 40px;
  //       background: rgba(22, 28, 40, 0.32);
  //       .single-distribution {
  //         width: 50%;
  //         height: 100%;
  //         text-align: left;
  //         position: relative;
  //         .single-graph-title {
  //           font-weight: bold;
  //           font-size: 32px;
  //           line-height: 40px;
  //           letter-spacing: 0px;
  //           .avg-title {
  //             display: inline-block;
  //             margin-left: 24px;
  //             color: rgba(255, 255, 255, 0.7);
  //             font-family: Microsoft YaHei;
  //             font-weight: bold;
  //             font-size: 24px;
  //             line-height: 40px;
  //             letter-spacing: 0px;
  //             text-align: left;
  //           }
  //           .avg-num {
  //             display: inline-block;
  //             margin-left: 24px;
  //             color: #49e5fa;
  //             font-family: Microsoft YaHei;
  //             font-weight: bold;
  //             font-size: 24px;
  //             line-height: 40px;
  //             letter-spacing: 0px;
  //             text-align: left;
  //           }
  //         }
  //         .basic-chart {
  //           height: 87%;
  //           width: 100%;
  //         }
  //       }
  //     }
  //     .current-amounts {
  //       width: 44%;
  //       height: 100%;
  //       .map-charts {
  //         width: 100%;
  //         height: 1200px;
  //       }
  //       .middle-digital-span {
  //         margin-top: 38px;
  //       }
  //     }
  //     .content-title {
  //       background: url("../../assets/images/fs-title-bg.png") no-repeat;
  //       background-size: 100% 100%;
  //       width: 40%;
  //       height: 15%;
  //       margin: 0 auto;
  //       text-align: center;
  //     }
  //     .accruing-amounts {
  //       .line-chart {
  //         height: 90%;
  //         padding-top: 2%;
  //       }
  //       .bottom-title-div {
  //         display: flex;
  //         justify-content: space-between;
  //         padding-top: 20px;
  //         .bottom-title {
  //           padding-left: 40px;
  //           width: 50%;
  //           height: 20px;
  //         }
  //       }
  //       .person-columnar {
  //         height: 530px;
  //         padding-left: 30px;
  //         display: inline-block;
  //         width: 50%;
  //         &:first-child {
  //           margin-right: 5%;
  //         }
  //       }
  //       .right-top-distribution {
  //         width: 100%;
  //         height: 320px;
  //         margin-top: 48px;
  //       }
  //       .right-middle-div,
  //       .right-bottom-div {
  //         display: flex;
  //       }
  //       .half-middle-distribution {
  //         width: 50%;
  //         height: 332px;
  //         margin-top: 40px;
  //       }
  //       .half-bottom-distribution {
  //         height: 426px;
  //         width: 50%;
  //         margin-top: 40px;
  //       }
  //     }
  //     .accruing-person {
  //       .columnar-chart {
  //         margin-top: 48px;
  //         height: 40%;
  //         margin-top: 48px;
  //       }
  //       .distribution {
  //         display: flex;
  //         height: 40%;
  //         padding-bottom: 20px;

  //         .left-distribution {
  //           height: 400px;
  //         }
  //         .right-distribution {
  //           height: 400px;
  //         }

  //         &:first-child {
  //           padding-bottom: 40px;
  //         }
  //       }
  //       .middle-distirbution {
  //         height: 394px;
  //         margin-top: 48px;
  //       }
  //       .bottom-distribution {
  //         height: 440px;
  //       }
  //       .form-charts {
  //         width: 50%;
  //         height: 400px;
  //       }
  //     }
  //   }
}
</style>