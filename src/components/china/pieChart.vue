<template>
  <div class="pie-echarts" :id="ids"></div>
</template>
<script>
export default {
  name: "education",
  props: ["ids", "chartData"],
  mounted() {
    this.initPie(this.ids, this.chartData);
  },
  data() {
    return {};
  },
  computed: {},
  methods: {
    initPie(curId, chartData) {
      const colorList = [
        "rgba(0,87,248,1)",
        "rgba(30,147,255,1)",
        "rgba(0,247,255,1)",
        "#FBD444",
        "#7F6AAD",
        "#585247"
      ];

      if (!curId) return;
      let chart = this.$echarts.init(document.getElementById(curId));
      chart.setOption({
        tooltip: {
          trigger: "item",
          backgroundColor: "rgba(70,130,180,0.8)",
          borderColor: "rgba(47,79,79,1)",
          borderWidth: 1,
          padding: [12, 24],
          axisPointer: {
            type: "shadow",
            label: {
              backgroundColor: "#6a7985"
            }
          },
          textStyle: {
            color: "rgba(255, 255, 255, 0.8)",
            fontStyle: "normal",
            fontFamily: "微软雅黑",
            fontSize: 24
          },
          formatter: "{b}<br />{a}: {c}"
        },
        // legend: {
        //   orient: "horizontal",
        //   left: "center",
        //   bottom: "5%",
        //   itemGap: 64,
        //   itemWidth: 22,
        //   itemHeight: 40,
        //   data: this.type
        //     ? this.type.map((item, index) => {
        //         return {
        //           name: item,
        //           icon: "roundRect"
        //         };
        //       })
        //     : [
        //         {
        //           name: "南京a",
        //           icon: "roundRect"
        //         },
        //         {
        //           name: "南京b",
        //           icon: "roundRect"
        //         },
        //         {
        //           name: "南京c",
        //           icon: "roundRect"
        //         }
        //       ],
        //   textStyle: {
        //     color: "rgba(255, 255, 255, 0.5)",
        //     fontSize: 48
        //   }
        // },
        color: colorList,
        series: [
          {
            name: "数量",
            type: "pie",
            radius: [80, 130],
            center: ["50%", "50%"],
            labelLine: {
              normal: {
                length: 20,
                length2: 160,
                lineStyle: {
                  type: "solid",
                  width: 4
                }
              }
            },
            avoidLabelOverlap: true,
            stillShowZeroSum: true,
            minShowLabelAngle: 10,
            label: {
              alignTo: "edge", // label两端对称布局
              //  ECharts v4.6.0 版本起，提供了 'labelLine' 与 'edge' 两种新的布局方式
              margin: 90, // 布局为两端对称时候需要外边距防止图表变形 数值随意不要太大
              distanceToLabelLine: 0, // label距离引导线距离
              formatter: params => {
                return (
                  "{b| " +
                  params.name +
                  "}  " +
                  "\n" +
                  "{c|" +
                  params.value +
                  "亿}"
                );
              },
              borderWidth: 0,
              borderRadius: 4,
              padding: [0, -50],
              height: 50,
              fontSize: 12,
              align: "left",
              color: "#3494BD",
              rich: {
                b: {
                  fontSize: 24,
                  lineHeight: 24,
                  color: "rgba(255,255,255,.7)",
                  padding: [12, 0, 5, 0]
                },
                c: {
                  fontSize: 28,
                  lineHeight: 24,
                  color: "#fff",
                  padding: [12, 0, 25, 0]
                }
              }
              // position: "center"
            },
            // emphasis: {
            //   label: {
            //     show: true,
            //     fontSize: "20",
            //     lineHeight: 64,
            //     fontWeight: "bold",
            //     position: "center",
            //     formatter: function(params) {
            //       return (
            //         "{type| " +
            //         params.name +
            //         "}  " +
            //         "\n" +
            //         "{value|" +
            //         params.value +
            //         "}"
            //       );
            //     },
            //     rich: {
            //       type: {
            //         fontSize: 64,
            //         color: "rgba(255,255,255,.7)",
            //         padding: [15, 0, 5, 0]
            //       },
            //       value: {
            //         fontSize: 66,
            //         color: "#fff",
            //         padding: [15, 0, 5, 0]
            //       }
            //     }
            //   }
            // },
            // labelLine: {
            //   show: false
            // },
            itemStyle: {
              borderWidth: 3,
              borderColor: "#082b3a"
            },
            data: this.leftData
              ? this.leftData.map((item, index) => {
                  return {
                    name: this.type[index],
                    value: item
                  };
                })
              : [
                  { name: "政策性", value: 3.21 },
                  { name: "自营性", value: 5.35 }
                  // { name: "南京c", value: 100 }
                ]
          }
        ]
      });
      chart.on("click", params => {
        this.$store.commit("newDialogData", params.name);
        this.$store.commit("newDialogVisible", true);
      });
    }
  },
  components: {},
  watch: {
    chartData: function(newVal) {
      this.initPie(this.ids, newVal);
    }
  }
};
</script>

<style lang="less">
</style>
