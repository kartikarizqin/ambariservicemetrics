<template>
  <div>
    <Nav_Menu/>
    <b-row>
      <b-col sm="3">
        <Nav_Vertical/>
      </b-col>
      <b-col sm="9" style="background-color:lightgrey">
        <b-container class="con-main">
          <b-nav id="navmetrics" class="mt-4">
            <b-nav-item href="/#/">METRICS</b-nav-item>
            <b-nav-item active href="/#/Heatmaps_Host">HEATMAPS</b-nav-item> 
            <b-nav-item href="/#/ConfigHist">CONFIG HISTORY</b-nav-item> 
          </b-nav>
          <Nav_Metrics/>
          <Dropdown/>
          <b-container id="cont_heatmaps" class="p-4">
            <b-card header="HDFS" header-class="header">
              <div v-for="bar in bars" class="mb-1">
                <p> <b> {{bar.text}} </b> </p>
                <b-container id="borderProgress" class="p-3 mb-3">
                  <p> Default Track </p>
                <b-progress height=30px style="border:1px solid #CBCBCB">
<b-progress-bar show-progress v-if="bar.data==='Invalid Data'"
                      :value="bar.value"
                      :label="' '+bar.data+bar.size"
                      :size="bar.size"
                      :striped="false"
                      :animated="false"
                      :data="bar.data"
                      variant="secondary"
                      style="color:black; font-weight:bold;"
                    ></b-progress-bar>
                      <b-progress-bar show-progress v-else-if="bar.data==='Data Not Available'"
                      :value="bar.value"
                      :label="' '+bar.data+bar.size"
                      :size="bar.size"
                      :striped="true"
                      :animated="false"
                      :data="bar.data"
                      variant="dark"
                      style="color:white; font-weight:bold;"
                    ></b-progress-bar>
                      <b-progress-bar show-progress v-else-if="bar.value>0 && bar.value <=20"
                      :value="bar.value"
                      :label="' '+bar.data+bar.size"
                      :size="bar.size"
                      :striped="true"
                      :animated="true"
                      :data="bar.data"
                      variant="info"
                      style="color:white; font-weight:bold;"
                    ></b-progress-bar>
                      <b-progress-bar show-progress v-else-if="bar.value>20 && bar.value <=40"
                      :value="bar.value"
                      :label="' '+bar.data+bar.size"
                      :size="bar.size"
                      :striped="true"
                      :animated="true"
                      :data="bar.data"
                      variant="success"
                      style="color:white; font-weight:bold;"
                    ></b-progress-bar>
                      <b-progress-bar show-progress v-else-if="bar.value>40 && bar.value <=60"
                      :value="bar.value"
                      :label="' '+bar.data+bar.size"
                      :size="bar.size"
                      :striped="true"
                      :animated="true"
                      :data="bar.data"
                      variant="warning"
                      style="color:white; font-weight:bold;"
                    ></b-progress-bar>
                      <b-progress-bar show-progress v-else-if="bar.value>60 && bar.value <=80"
                      :value="bar.value"
                      :label="' '+bar.data+bar.size"
                      :size="bar.size"
                      :striped="false"
                      :animated="false"
                      :data="bar.data"
                      variant="warning"
                      style="color:white; font-weight:bold;"
                    ></b-progress-bar>
                      <b-progress-bar show-progress v-else-if="bar.value>80 && bar.value <=100"
                      :value="bar.value"
                      :label="' '+bar.data+bar.size"
                      :size="bar.size"
                      :striped="true"
                      :animated="true"
                      :data="bar.data"
                      variant="danger"
                      style="color:white; font-weight:bold;"
                    ></b-progress-bar>
                </b-progress>
                </b-container>
              </div>
              <b-btn href="/#/Heatmaps_HDFS">&lsaquo;</b-btn>
              <b-btn disabled href="">&rsaquo;</b-btn>
          </b-card>
        </b-container>
      </b-container>
    </b-col>
    </b-row>
  </div>
</template>

<script>
import Nav_Menu from './Main/Nav_Menu';
import Nav_Vertical from './Main/Nav_Vertical';
import Nav_Metrics from './Main/Nav_Metrics';
import Progress from './Heatmaps/Progress';
import Dropdown from './Heatmaps/Dropdown';
import ProgressBar from 'vue-simple-progress'
export default {
  data () {
    return {
      Nav_Menu,
      Nav_Vertical,
      Nav_Metrics,
      Progress,
      Dropdown,
      // value:[75, 32.5,10],
      bars: [
        {variant: 'success', value: (9000/50000)*100, data:9000, text:"DataNode Process Disk I/O Utilization (MB)", size:" MB used of 50000 MB", striped:true, animated:true},
        {variant: 'success', value:(20/100)*100, data:20, text:"DataNode Network I/O Utilization (%)", size:" % from 100%", striped:true, animated:true},
        {variant: 'success', value: (15/100)*100, data:15, text:"HDFS Space Utilization (%)",size:" % from 100%", striped:true, animated:true},
        {variant: 'success', value: (200/1024)*100, data:200, text:"HDFS Bytes Read (MB)", size:" MB used of 1024 MB", striped:true, animated:true},
        
      ],
      timer: null
    }
  },
  components: {
    Nav_Menu,
    Nav_Vertical,
    Nav_Metrics,
    Progress,
    Dropdown,
    ProgressBar,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.button{
    min-width: 40%;
    background: rgba(247, 249, 249,0.7);
    border: 1px solid gray;
    color: black;
}
.button a.active{
    color:red;
}
.button:hover{
    background: lightgray;
}
p{
    text-align: left;
}
#borderProgress{
  border: 1px solid lightgray;
  border-radius: 5px;
  padding: 10px;
}
.header{
  font-weight: bold;
  font-size: 20px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
#navmetrics{
  background: lightgray;
}
#navmetrics a{
  background: lightgrey;
  color: black;
  border-radius: 8px 8px 0px 0px;
}
#navmetrics a.active{
  background: white;
  color: black;
}
#navmetrics a:hover{
  background: rgba(253, 253, 253, 0.3);
  color: black;
  font-weight: bold;
}
</style>