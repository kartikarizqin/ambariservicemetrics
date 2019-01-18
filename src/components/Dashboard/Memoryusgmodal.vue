<template>
  <div>
    <div class="containers">
      <b-dropdown right split text="Last 1 Hour" id="ddown-sm-split" size="sm" style="margin-top:10px; font-size:14px" variant="light">
        <b-dropdown-item> Last 1 Hour</b-dropdown-item>
        <b-dropdown-item> Last 2 Hour</b-dropdown-item>
        <b-dropdown-item> Last 4 Hour</b-dropdown-item>
        <b-dropdown-item> Last 12 Hour</b-dropdown-item>
        <b-dropdown-item> Last 24 Hour</b-dropdown-item>
        <b-dropdown-item> Last 1 Week</b-dropdown-item>
        <b-dropdown-item> Last 1 Month</b-dropdown-item>
        <b-dropdown-item> Last 2 Year</b-dropdown-item>
        <b-dropdown-item> Custom</b-dropdown-item>
      </b-dropdown>
      <v-icon name="download" color="black" style="margin-left:10px"/>
      <line-example 
        :options="{responsive: false, maintainAspectRatio: false}"
        :height=300>
      </line-example>
    </div>
    <b-table striped hover :items="items"></b-table>
  </div>
</template>

<script>
import LineExample from './MemoryUsageChart.js';
import Memoryusg from './Memoryusg'

const items = [
  { Labels: 'Use_avg', min: 4.5, avg: 4.8, max: '5 KB' },
  { Labels: 'Total_avg', min: 8, avg: 8, max: '8 KB' },
  { Labels: 'Swap_avg', min: 2.5, avg: 2.7, max: '3 KB' },
  { Labels: 'Others_avg', min: 0.5, avg: 0.5, max: '0.5 KB' },
]

export default {
  name: 'apps',
  components: {
    LineExample
  },
  data () {
    return {
      items: items
    }
  }
}
</script>

<style>
.containers {
  max-width: 300px;
  max-height: 300px;
  margin:  0 auto;
}
</style>