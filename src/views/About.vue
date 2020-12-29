<template>
  <div class="about" id="about">
    <h1>This is an about page</h1>
    <div id="main" style="width: 600px;height:400px;"></div>
  </div>
</template>
<script>
var echarts = require('echarts');
export default {
  name: "app",
  data() {
    return {
      option: {
        title: {
          text: "ECharts 入门示例"
        },
        tooltip: {},
        legend: {
          data: ["销量"]
        },
        xAxis: {
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "pie",
            data: [19, 20, 36, 10, 10, 20]
          }
        ]
      }
    };
  },
  methods: {
    drawPid(id) {
      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById(id));
      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(this.option);
    }
  },
  mounted() {
    this.$nextTick(function() {
      this.drawPid("main");
    });
  }
};
</script>
