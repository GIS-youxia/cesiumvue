<template>
  <div id="chart5">

  </div>
</template>

<script>

import { inject, onMounted } from 'vue'
export default {
  setup() {
    let $echarts = inject("echarts")
    onMounted(() => {
      let myChart = $echarts.init(document.getElementById("chart5"))
      myChart.setOption({
        graphic: {
          elements: [
            {
              type: 'text',
              left: 'center',
              top: 'center',
              style: {
                text: '智慧大屏演示',
                fontSize: 60,
                fontWeight: 'bold',
                lineDash: [0, 200],
                lineDashOffset: 0,
                fill: 'transparent',
                stroke: '	#000000',
                lineWidth: 1
              },
              keyframeAnimation: {
                duration: 3000,
                loop: true,
                keyframes: [
                  {
                    percent: 0.7,
                    style: {
                      fill: 'transparent',
                      lineDashOffset: 200,
                      lineDash: [200, 0]
                    }
                  },
                  {
                    // Stop for a while.
                    percent: 0.8,
                    style: {
                      fill: '	#FFFFFF'
                    }
                  },
                  {
                    percent: 1,
                    style: {
                      fill: '#000000'
                    }
                  }
                ]
              }
            }
          ]
        }
      })
    })
    return {}
  }


}
</script>

<style>
#chart5 {
  width: 100%;
  height: 1rem;
}
</style>