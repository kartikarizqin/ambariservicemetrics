<template>
  <div>
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
    <pie-chart
      :chart-data="datacollection"
      :height="280">
    </pie-chart>
    <p class="text-md-center">Used 1% (3 MB of 3 GB)</p>
    <p class="text-md-center">Not Used 99% (2997 MB of 3 GB)</p>
  </div>
</template>

<script src="https://www.gstatic.com/charts/loader.js"></script>
<script>
import PieChart from './PieChart.js';
import YARNMemory from './YARNMemory'

  export default {
    components: {
      PieChart
    },
    data () {
      return {
        datacollection: null
      }
    },
    mounted () {
      this.fillData()
    },
    methods: {
      fillData () {
        this.datacollection = {
        labels: ['Used', 'Free'],
          datasets: [
            {
              backgroundColor: ['#FE4E7A','#3CB7F8'],
              data: [99, 1]
            },
          ]
        }
      }
    }
  }
</script>

<style scoped>
</style>