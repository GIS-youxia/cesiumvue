<template>
  <div id="chart1">

  </div>
</template>

<script>

import { inject, onMounted } from 'vue'
export default {
  setup() {
    let $echarts = inject("echarts")
    onMounted(() => {
      let myChart = $echarts.init(document.getElementById("chart1"))
      myChart.setOption({
        title: {
          text: '各市GDP对比',
          left: 'center',
          textStyle: {
            color: '#ccc'
          }
        },
        xAxis: {
          type: "category",
          data: ["郑州", "武汉", "西安", "合肥"],

        },
        yAxis: {
          type: "value",

        },
        series: {

          type: "bar",
          data: ["1.27", "1.77", "1.07", "1.14"],

        }
      })
    })
    return {}
  }


}
</script>

<style>
#chart1 {
  position: absolute;
  left: 10px;
  width: 6rem;
  height: 4rem;
}
</style>