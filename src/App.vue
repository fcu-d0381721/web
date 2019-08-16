<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>{{ data }}</h1>
    <test></test>
    <ve-line v-bind:data="chartData" :settings="chartSettings"></ve-line>
    <div class="btn" v-on:click="changeData">改變資料</div>
  </div>
</template>

<script>

import test from './components/test'
import VeLine from 'v-charts/lib/line.common'

export default {
  name: 'app',
  data() {
    return {
      data: "hihi",
      chartData: {
          columns: ['日期', '访问用户', '下单用户', '下单率'],
          rows: [
            { '日期': '1/1', '访问用户': 1393, '下单用户': 1093, '下单率': 0.32 },
            { '日期': '1/2', '访问用户': 3530, '下单用户': 3230, '下单率': 0.26 },
            { '日期': '1/3', '访问用户': 2923, '下单用户': 2623, '下单率': 0.76 },
            { '日期': '1/4', '访问用户': 1723, '下单用户': 1423, '下单率': 0.49 },
            { '日期': '1/5', '访问用户': 3792, '下单用户': 3492, '下单率': 0.323 },
            { '日期': '1/6', '访问用户': 4593, '下单用户': 4293, '下单率': 0.78 }
          ]
        }
    }
  },components: {
    test,VeLine
  },methods: {
    changeData: function(){
      this.chartData.rows[1].下单率 += 100
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.btn {
  cursor: pointer;
}
</style>
