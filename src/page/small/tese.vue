<template>
  <div class="container">
    <!-- 头部 -->
    <!-- <div class="title-frame">
      <div class="title-left"></div>
      <div class="global-title">中国进出口银行</div>
      <div class="right-time"></div>
    </div>-->
    <div
      v-for="item in 9"
      :key="item"
      :class="'control-div  control-div' + item"
      @click="jump(item)"
    ></div>
  </div>
</template>

<script>
import Vue from "vue";
export default {
  mounted() {},
  data() {
    return {};
  },
  computed: {},
  methods: {
    jump(key) {
      let temp = "";
      switch (key) {
        case 1:
          temp = "/zhongxiaowei";
          break;
        case 2:
          temp = "/yidaiyilu";
          break;
        case 3:
          temp = "/minying";
          break;
        case 4:
          temp = "/duiwai";
          break;
        case 5:
          temp = "/shengji";
          break;
        case 6:
          temp = "/zouchuqu";
          break;
        case 7:
          temp = "/lvse";
          break;
        case 8:
          temp = "/zhengcexing";
          break;
        case 9:
          temp = "/zhizao";
          break;
        default:
          temp = "/home";
          break;
      }
      this.$router.push("/manage" + temp);
    }
  },
  beforeDestroy() {},
  components: {}
};
</script>

<style lang="less" scoped>
.container {
  width: 3840px;
  height: 2160px;
  position: relative;
  
  background: url("../../assets/images/home/tese.png") no-repeat;
  background-size: 100% 100%;
  font-size: 28px;
  color: #fff;
  overflow: hidden;
  font-family: Microsoft YaHei;

  .control-div {
    position: absolute;
    width: 950px;
    height: 300px;
    cursor: pointer;
  }
  .control-div1 {
    left: 400px;
    top: 330px;
  }
  .control-div2 {
    left: 2540px;
    top: 330px;
  }
  .control-div3 {
    left: 180px;
    top: 690px;
  }
  .control-div4 {
    left: 2680px;
    top: 690px;
  }
  .control-div5 {
    left: 180px;
    top: 1070px;
  }
  .control-div6 {
    left: 2680px;
    top: 1070px;
  }
  .control-div7 {
    left: 400px;
    bottom: 400px;
  }
  .control-div8 {
    left: 2540px;
    bottom: 400px;
  }
  .control-div9 {
    left: 1440px;
    bottom: 100px;
  }

  // 标题样式
  //   .title-frame {
  //     width: 100%;
  //     height: 7%;
  //     background: url("../../assets/images/home/header.png") no-repeat;
  //     background-size: 100% 100%;
  //     display: flex;
  //     justify-content: space-between;
  //     padding: 0 1%;
  //     .title-left {
  //       width: 33%;
  //     }
  //     .global-title {
  //       text-align: center;
  //       width: 33%;
  //       padding-top: 24px;
  //       font-size: 64px;
  //       font-weight: bold;
  //       font-family: FZZhengHeiS-B-GB;
  //     }
  //     .right-time {
  //       width: 33%;
  //       text-align: right;
  //     }
  //   }
}
</style>