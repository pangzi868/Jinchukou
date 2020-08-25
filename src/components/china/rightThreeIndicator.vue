<template>
  <div class="right-indicator">
    <div v-for="item in data" :key="item.key" class="single-indicator">
      <img class="huan-img" :src="item.img" alt />
      <!-- <img class="huan-icon" :src="Icon1" alt /> -->
      <div class="right">
        <div class="title">{{item.name}}</div>
        <div class="value">{{item.value}}</div>
        <span class="unit">亿</span>
        <span class="unit">环比</span>
        <div class="value-num">{{item.num}}</div>
      </div>
    </div>
  </div>
</template>

<script>
import huan from "../../assets/images/Untitled-huan1.png";
import icon5 from "../../assets/images/jinchukou/bulianglv.png";
import icon1 from "../../assets/images/jinchukou/buliangzichan.png";
export default {
  name: "",
  props: [],
  mounted() {},
  data() {
    return {
      Huan: huan,
      Icon5: icon5,
      Icon1: icon1,
      data: [
        {
          name: "贷款发放",
          value: "1,620.13",
          key: "dai1",
          num: "2.34%",
          img: icon5
        },
        {
          name: "贷款签约",
          value: "1,620.13",
          key: "lei1",
          num: "12.4%",
          img: icon1
        }
      ]
    };
  },
  computed: {},
  methods: {},
  components: {}
};
</script>

<style lang="less" scoped>
.right-indicator {
  .single-indicator {
    position: relative;
    height: 168px;
    width: 100%;
    margin-bottom: 16px;
    background: url("../../assets/images/jinchukou/xiaohu.png") no-repeat;
    background-size: 100% 100%;
    padding: 12px;
    .huan-img {
      margin-right: 14px;
      display: inline-block;
      width: 48px;
      height: 48px;
      vertical-align: top;
    }
    .huan-icon {
      position: absolute;
      top: 30px;
      left: 30px;
      width: 48px;
      height: 48px;
    }
    .right {
      display: inline-block;
      width: 70%;
      .title {
        color: rgba(255, 255, 255, 1);
        font-family: Microsoft YaHei;
        font-weight: regular;
        font-size: 32px;
        line-height: normal;
        letter-spacing: 0px;
        text-align: left;
      }
      .value {
        display: inline-block;
        color: rgba(255, 166, 101, 1);
        font-family: Microsoft YaHei;
        font-weight: bold;
        font-size: 34px;
        margin-right: 14px;
        line-height: normal;
        letter-spacing: 0px;
        text-align: left;
      }
      .value-num {
        display: inline-block;
        margin-left: 14px;
        color: #fff;
        font-family: Microsoft YaHei;
        font-weight: bold;
        font-size: 32px;
        line-height: normal;
        letter-spacing: 0px;
        text-align: left;
      }
      .unit {
        display: inline-block;
        color: rgba(255, 255, 255, 0.7);
        font-family: Microsoft YaHei;
        font-weight: regular;
        font-size: 24px;
        line-height: normal;
        letter-spacing: 0px;
        text-align: left;
        // margin-right: 70px;
      }
    }
  }
}
</style>
