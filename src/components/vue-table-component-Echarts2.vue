<template>
  <div id="chart2">

  </div>
</template>

<script>
import { inject, onMounted } from 'vue'
export default {
  setup() {
    let $echarts = inject("echarts")
    onMounted(() => {
      let myChart = $echarts.init(document.getElementById("chart2"))
      myChart.setOption({
        title: {
          text: '郑州历年人均GDP',
          left: 'center',
          textStyle: {
            color: '#ccc'
          }
        },
        xAxis: {
          type: 'category',
          boundaryGap: false,
          data: ['2015', '2016', '2017', '2018', '2019', '2020', '2021']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            name: "z",
            data: [7.71, 8.28, 9.37, 10.13, 11.31, 9.52, 9.96],
            type: 'line',
            areaStyle: {},
            smooth: true
          }
        ]
      })
    })
    return {}
  }


}
</script>

<style>
#chart2 {
  width: 6rem;
  height: 4rem;

}
</style>