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
import LineExample from './CPUUsgChart.js';
import CPUusg from './CPUusg'

const items = [
  { Labels: 'User_avg', min: 10, avg: 16.3, max: '20 KB' },
  { Labels: 'System_avg', min: 2, avg: 3.5, max: '5 KB' },
  { Labels: 'Nice_avg', min: 2, avg: 3.5, max: '5 KB' },
  { Labels: 'Idle_avg', min: 97, avg: 98.8, max: '100 KB' },
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