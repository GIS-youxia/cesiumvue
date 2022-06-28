<template>
  <div id="chart4">

  </div>
</template>

<script>

import { inject, onMounted } from 'vue'
export default {
  setup() {
    let $echarts = inject("echarts")
    onMounted(() => {
      let myChart = $echarts.init(document.getElementById("chart4"))
      myChart.setOption({
        title: {
          text: '郑州市气温',
          left: 'center',
          textStyle: {
            color: '#ccc'
          }
        },
        series: [
          {
            type: 'gauge',
            progress: {
              show: true
            },
            pointer: {
              itemStyle: {
                color: '#FF0000'
              }
            },
            axisLabel: {
              color: '#F29000',

            },
            detail: {
              valueAnimation: true,
              formatter: '{value}',
              color: '#FF3333'
            },
            data: [
              {
                value: 39,
              }
            ]
          }
        ]
      })
    })
    return {}
  }


}
</script>

<style>
#chart4 {
  width: 6rem;
  height: 4rem;

}
</style>