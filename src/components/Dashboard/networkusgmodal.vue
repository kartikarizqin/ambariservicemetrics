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
import LineExample from './NetworkUsageChart.js';
import networkusg from './networkusg';

const items = [
  { Labels: 'Output_avg', min: 0, avg: 45.8, max: '100 KB' },
  { Labels: 'Input_avg', min: 20, avg: 47.5, max: '75 KB' }
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
  max-height: 300px;
  margin:  0 auto;
}

</style>