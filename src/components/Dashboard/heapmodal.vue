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
      :chartData="datacollection"
      :height="280"
      :option="myoption"
      >
    </pie-chart>
    <p class="text-md-center">Used 54% (545 MB of 1103 MB)</p>
    <p class="text-md-center">Not Used 66% (558 MB of 1103 MB)</p>
    <!-- <b-table striped hover :items="items"></b-table> -->
  </div>
</template>

<script src="https://www.gstatic.com/charts/loader.js"></script>
<script>
import PieChart from './PieChart.js'

  export default {
    components: {
      PieChart
    },
    data () {
      return {
        datacollection: null,
      }
    },
    mounted () {
      this.datacollection = {
          labels:['Used', 'Not Used'],
          datasets: [
            {
              backgroundColor: ['#5CD2B2', '#FA9A14'],
              data: [54,66],
              hoverBackgroundColor: ['#5CD2B2', '#FA9A14'],
              hoverBorderColor:"black",
              borderwidth:2
            }
          ],
  
        },{
          options:{
            mode:'percentage',
            precision:1
          }
        }
      }
    }
    
</script>

<style scoped>
</style>