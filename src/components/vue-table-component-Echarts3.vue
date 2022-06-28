<template>
  <div id="chart3">

  </div>
</template>

<script>
import { inject, onMounted } from 'vue'
export default {
  setup() {
    let $echarts = inject("echarts")
    onMounted(() => {
      let myChart = $echarts.init(document.getElementById("chart3"))
      myChart.setOption({
              title: {
    text: '各市人口对比',
    left: 'center',
    textStyle:{
      color: '#ccc'
    }
  },
     legend: {
    top: 'bottom'
  },
  toolbox: {
    show: true,
    feature: {
      mark: { show: true },
      dataView: { show: true, readOnly: false },
      restore: { show: true },
      saveAsImage: { show: true }
    }
  },
  series: [
    {
      name: 'Nightingale Chart',
      type: 'pie',
      radius: [10, 75],
      center: ['50%', '50%'],
      roseType: 'area',
      itemStyle: {
        borderRadius: 5
      },
      data: [
        { value: 1274, name: '郑州' },
        { value: 706, name: '洛阳' },
        { value: 1003, name: '南阳' },
        { value: 438, name: '许昌' },
        { value: 250, name: '开封' },
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
#chart3 {
  width: 6rem;
  height: 4rem;

}
</style>