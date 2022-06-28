<template>
  <div id="top">
  <div  id="table5">
<Echarts5></Echarts5>
  </div>
   
  </div>
  <div id="mapDiv">
    <Earth></Earth>
  </div>
  <div id="timeDiv">
    <img src="../时间.png" id="timePng">
    <div id="timeVue">
      <Time>
      </Time>
    </div>
  </div>
  <div>
<img src="../图表装饰.png" id="tableTop1">
    <div class="table" id="table1">
      <Echarts1>
      </Echarts1>
    </div>
  </div>
  <div>
    <div class="table" id="table2">
      <Echarts2>
      </Echarts2>
    </div>
  </div>
  <div>
    <div class="table" id="table3">
      <Echarts3>
      </Echarts3>
    </div>
  </div>
  <div>
    <div class="table" id="table4">
      <Echarts4>
      </Echarts4>
    </div>
  </div>


</template>

<script>
import { provide } from "vue"
import * as echarts from "echarts"
import axios from "axios"
import Earth from './components/vue-map-component-Earth.vue'
import Time from './components/vue-time-component-time.vue'
import Echarts1 from './components/vue-table-component-Echarts1.vue'
import Echarts2 from './components/vue-table-component-Echarts2.vue'
import Echarts3 from './components/vue-table-component-Echarts3.vue'
import Echarts4 from './components/vue-table-component-Echarts4.vue'
import Echarts5 from './components/vue-table-component-Echarts5.vue'
import { inject } from "vue"

export default {
  setup() {
    provide("echarts", echarts)
    provide("axios", axios)
    let $echarts = inject("echarts")
    let $axios = inject("axios")
    console.log($echarts)
    console.log($axios)
  },
  components: {
    Earth,
    Time,
    Echarts1,
    Echarts2,
    Echarts3,
    Echarts5,
    Echarts4
  }
}
</script>

<style>
html,
body {
  margin: 0;
  background-color: black;
}

#timePng {
  width: 0.3rem;
  height: 0.3rem;

}


#top {
  width: 100%;
  height: 1rem;
  text-align: center;
  background: linear-gradient(rgb(82, 105, 233), rgb(63, 175, 209));
  /* opacity: 0.2; */
}

#timeDiv {
  margin: 0;
  position: absolute;
  z-index: 2;

}

#mapDiv {
  margin: 0;
  position: absolute;
  width: 100%;
 /* display: none; */
  z-index: -1;
}

#table1 {
  left: 0;
  top: 1.65rem;
}

#table2 {
  right: 0;
  top: 1.65rem;
}

#table3 {
  left: 0;
  top: 6rem;
  z-index: 3;
}

#table4 {
  right: 0;
  top: 6rem;
  z-index: 3;
}
#table5 {
  z-index: 30;
}

#timeVue {
  float: right;
}

#tableTop1{
  position: absolute;
  top:1.65rem;
  width: 6rem;
  height: 0.5rem;
  z-index: 1;
}

.table {
  top: 0;
  position: absolute;
  z-index: 2;
  width: 6rem;
  height: 4rem;
  border: 1px solid seashell;

}
</style>

