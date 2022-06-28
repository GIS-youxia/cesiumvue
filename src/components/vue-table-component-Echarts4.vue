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
    textStyle:{
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
          color: '#37a2da'
        }
      },
      axisLabel: {
        color: '#37a2da',
       
      },
      detail: {
        valueAnimation: true,
        formatter: '{value}',
        color:'#37a2da'
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