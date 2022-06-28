<template>
  <div>
    <table class="excel">
      <thead>
        <tr>

          <th>年份</th>
          <th>出省游客人数</th>
          <th>进省游客人数</th>
          <th>门票收入</th>

        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in stu" :key="index">

          <td>
            <div>{{ item.year }}</div>

          </td>
          <td>
            <div>{{ item.out }}</div>

          </td>
          <td>
            <div>{{ item.in }}</div>

          </td>
          <td>
            <div>{{ item.price }}</div>

          </td>
          <td>

          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script>
import { reactive } from "vue";

export default {
  setup() {
    let stu = reactive([
      { year: "2022", out: 14557, in: 194545, price: "6.55" },
      { year: "2021", out: 15787, in: 19545, price: "6.33" },
      { year: "2020", out: 174556, in: 20543, price: "6" },
      { year: "2019", out: 175645, in: 26545, price: "7" },
      { year: "2018", out: 174554, in: 28776, price: "8" },

    ]);


    return {
      stu,

    };
  },
};
</script>

<style >
thead {
  color: #FFFFFF;
  font-size: 20PX;
  background-color: rgba(17, 73, 183, 0.5);
}

tbody {
  color: #FFFFFF;
  font-size: 20PX;
}

.excel {
  position: absolute;
  border-collapse: collapse;
  background-color: rgba(255, 255, 255, 0.2);
  text-align: center;
  height: 200px;
  width: 11rem;
  left: 6.5rem;
  bottom: 100PX;
}
</style>
