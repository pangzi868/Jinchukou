<template>
  <div class="container">
    <!-- 头部 -->
    <div class="title-frame">
      <div class="title-left"></div>
      <div class="global-title">中国进出口银行</div>
      <div class="right-time"></div>
    </div>
    <!-- <world-chart class="world-chart" /> -->
    <div class="side-div left-side">
      <div class="left-one">
        <div class="content-title-frame">贷款实时分析</div>
        <div class="content-frame">
          <left-indicator class="left-indicator" />
        </div>
      </div>
      <div class="left-two">
        <div class="content-title-frame">资产规模分析</div>
        <div class="content-frame">
          <column-box class="column-box" ids="left2" :chartData="[]" />
          <column-indicator class="column-indicator" :chartData="[]" />
        </div>
      </div>
      <div class="left-three">
        <div class="content-title-frame">每月走势图</div>
        <div class="content-frame">
          <column-line class="column-line" ids="left3" :chartData="[]" />
        </div>
      </div>
    </div>
    <img class="tese-img" :src="Tese" alt @click="jump"/>
    <map-chart class="map-charts" />
    <div class="bottom-left-ind">
      <span class="ind-name">巴黎分行</span>
      <span class="ind-val">50亿</span>
    </div>
    <div class="bottom-side">
      <div class="bottom-title">政策性、自营性贷款分析</div>
      <div class="air-span"></div>
      <pie-chart class="pie-chart" ids="pieChart" :chartData="[]" />
      <img class="divisition" :src="Divisition" alt />
      <merge-column class="merge-chart" ids="mergeColumn" :chartData="[]" />
      <bottom-indicator class="bottom-indicator" />
    </div>
    <div class="side-div right-side">
      <div class="right-one">
        <div class="content-title-frame">资产效益</div>
        <div class="content-frame">
          <right-one-chart class="column-line" ids="right1" :chartData="[]" />
        </div>
      </div>
      <div class="right-two">
        <div class="content-title-frame">利息净收入</div>
        <div class="content-frame">
          <right-two-chart class="column-line" ids="right2" :chartData="[]" />
        </div>
      </div>
      <div class="right-three">
        <div class="content-title-frame">资产质量</div>
        <div class="content-frame">
          <right-three-indicator class="right-ind" />
          <right-line class="right-line" ids="right3Line" :chartData="[]" />
          <right-color-line class="right-color-line" ids="right3ColorLine" :chartData="[]" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import Tese from "../../assets/images/jinchukou/tese.png";
import Divisition from "../../assets/images/jinchukou/Rectangle-32@1x.png";

import LeftIndicator from "../../components/china/leftIndicator.vue";
import BottomIndicator from "../../components/china/bottomIndicator.vue";
import ColumnBox from "../../components/china/columnBox.vue";
import ColumnLine from "../../components/china/columnLine.vue";
import RightOneChart from "../../components/china/rightOneColumnLine.vue";
import RightLine from "../../components/china/rightLine.vue";
import RightColorLine from "../../components/china/rightColorLine.vue";
import RightTwoChart from "../../components/china/rightTwoColumnLine.vue";
import RightThreeIndicator from "../../components/china/rightThreeIndicator.vue";
import ColumnIndicator from "../../components/china/columnIndicator.vue";
import MapChart from "../../components/china/mapChart.vue";
import PieChart from "../../components/china/pieChart.vue";
import MergeColumn from "../../components/china/mergeColumnBox.vue";
export default {
  mounted() {},
  data() {
    return {
      Tese: Tese,
      Divisition: Divisition
    };
  },
  computed: {},
  methods: {
    jump() {
      this.$router.push('/manage/tese')
    }
  },
  beforeDestroy() {},
  components: {
    MapChart,
    LeftIndicator,
    BottomIndicator,
    ColumnBox,
    ColumnIndicator,
    ColumnLine,
    RightOneChart,
    RightTwoChart,
    RightThreeIndicator,
    RightLine,
    RightColorLine,
    PieChart,
    MergeColumn
  }
};
</script>

<style lang="less" scoped>
.container {
  width: 3840px;
  height: 2160px;
  position: relative;
  
  background: url("../../assets/images/jinchukou/bg@1x.png") no-repeat;
  background-size: 100% 100%;
  font-size: 28px;
  color: #fff;
  overflow: hidden;
  font-family: Microsoft YaHei;

  -ms-text-size-adjust: auto;
  -webkit-text-size-adjust: auto;
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

  .tese-img {
    height: 247.62px;
    width: 227.62px;
    position: absolute;
    top: 160px;
    left: 1000px;
    cursor: pointer;
    z-index: 10;
  }

  .bottom-left-ind {
    position: absolute;
    left: 1040px;
    top: 1500px;
    .ind-name {
      display: inline-block;
      margin-right: 40px;
      color: rgba(255, 255, 255, 0.8);
      font-family: Microsoft YaHei;
      font-weight: bold;
      font-size: 40px;
      line-height: normal;
      letter-spacing: 0px;
      text-align: left;
    }
    .ind-val {
      display: inline-block;
      margin-right: 40px;
      color: rgba(255, 171, 48, 1);
      font-family: Microsoft YaHei;
      font-weight: bold;
      font-size: 64px;
      line-height: normal;
      letter-spacing: 0px;
      text-align: left;
    }
  }

  .map-charts {
    position: absolute;
    left: 526px;
    top: 68px;
    width: 2802.92px;
    height: 1644px;
  }

  .side-div {
    width: 912px;
    height: 2000px;
    z-index: 10;
  }
  .left-side {
    position: absolute;
    top: 121px;
    left: 32px;
    .content-title-frame {
      background: url("../../assets/images/jinchukou/title2@1x.png") no-repeat;
      background-size: 100% 100%;
      padding: 24px 90px;
      width: 100%;
      color: rgba(255, 255, 255, 1);
      font-family: Noto Sans SC Bold;
      font-weight: regular;
      font-size: 42px;
      line-height: 64px;
      letter-spacing: 2px;
      text-align: left;
      height: 80px;
      margin-bottom: 16px;
    }
    .left-one {
      position: absolute;
      left: 0;
      top: 0;
      height: 443px;
      width: 100%;
      .content-frame {
        background: url("../../assets/images/jinchukou/bj-@1x.png") no-repeat;
        background-size: 100% 100%;
        width: 100%;
        height: 363px;
        .left-indicator {
          height: 100%;
          width: 100%;
          padding: 36px 72px;
        }
      }
    }
    .left-two {
      position: absolute;
      left: 0;
      top: 500px;
      height: 752px;
      width: 100%;
      .content-frame {
        background: url("../../assets/images/jinchukou/framebg2.png") no-repeat;
        background-size: 100% 100%;
        padding: 32px;
        width: 100%;
        height: 657px;
        .column-box {
          width: 826px;
          height: 360px;
        }
        .column-indicator {
          width: 100%;
          height: 166px;
          margin-top: 34px;
        }
      }
    }
    .left-three {
      position: absolute;
      left: 0;
      top: 1270px;
      height: 752px;
      width: 100%;
      .content-frame {
        background: url("../../assets/images/jinchukou/framebg2.png") no-repeat;
        background-size: 100% 100%;
        width: 100%;
        height: 657px;
        padding: 32px;
        .column-line {
          width: 100%;
          height: 100%;
        }
      }
    }
  }
  .bottom-side {
    position: absolute;
    width: 1828px;
    height: 521.38px;
    bottom: 32px;
    left: 1000px;
    background: url("../../assets/images/jinchukou/framebg2.png") no-repeat;
    background-size: 100% 100%;
    padding: 32px 48px;
    z-index: 10;
    .bottom-title {
      background: url("../../assets/images/jinchukou/frame-bk.png") no-repeat;
      background-size: 100% 100%;
      position: absolute;

      padding: 14px 32px;
      width: 94.5%;
      height: 80px;
    }
    .air-span {
      width: 100%;
      height: 100px;
    }
    .pie-chart {
      display: inline-block;
      width: 612px;
      height: 370px;
    }
    .merge-chart {
      display: inline-block;
      width: 700px;
      height: 370px;
      margin-left: 50px;
    }
    .bottom-indicator {
      display: inline-block;
      width: 354px;
      height: 370px;
      vertical-align: top;
    }
    .divisition {
      display: inline-block;
      width: 8px;
      height: 364px;
      vertical-align: top;
    }
  }
  .right-side {
    position: absolute;
    top: 121px;
    right: 32px;
    .content-title-frame {
      background: url("../../assets/images/jinchukou/title2@1x.png") no-repeat;
      background-size: 100% 100%;
      padding: 24px 90px;
      width: 100%;
      color: rgba(255, 255, 255, 1);
      font-family: Noto Sans SC Bold;
      font-weight: regular;
      font-size: 42px;
      line-height: 64px;
      letter-spacing: 2px;
      text-align: left;
      height: 80px;
      margin-bottom: 16px;
    }
    .right-one {
      position: absolute;
      left: 0;
      top: 0;
      height: 443px;
      width: 100%;
      .content-frame {
        background: url("../../assets/images/jinchukou/framebg2.png") no-repeat;
        background-size: 100% 100%;
        width: 100%;
        padding: 32px;
        height: 363px;
        .column-line {
          width: 100%;
          height: 100%;
        }
      }
    }
    .right-two {
      position: absolute;
      left: 0;
      top: 500px;
      height: 443px;
      width: 100%;
      .content-frame {
        background: url("../../assets/images/jinchukou/framebg2.png") no-repeat;
        background-size: 100% 100%;
        width: 100%;
        height: 379px;
        padding: 32px;
        .column-line {
          width: 100%;
          height: 100%;
        }
      }
    }
    .right-three {
      position: absolute;
      left: 0;
      top: 1000px;
      height: 1030px;
      width: 100%;
      .content-frame {
        background: url("../../assets/images/jinchukou/framebg2.png") no-repeat;
        background-size: 100% 100%;
        width: 100%;
        height: 927px;
        padding: 32px;
        .right-ind {
          display: inline-block;
          width: 280px;
          height: 352px;
          vertical-align: top;
          margin-right: 24px;
        }
        .right-line {
          display: inline-block;
          width: 536px;
          height: 352px;
        }
        .right-color-line {
          width: 100%;
          height: 402px;
          margin-top: 50px;
        }
      }
    }
  }
}
</style>