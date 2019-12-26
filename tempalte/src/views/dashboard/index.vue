<template>
  <div class="dashboard-editor-container">
    <el-row style="background:#fff;padding:10px">
      <line-chart :chart-data="lineChartData" width="24%" height="200px" />
      <line-chart :chart-data="lineChartData" width="24%" height="200px" />
      <line-chart :chart-data="lineChartData" width="24%" height="200px" />
      <line-chart :chart-data="lineChartData" width="24%" height="200px" />
    </el-row>
  </div>
</template>

<script>
import LineChart from './components/LineChart'

const lineChartData = {
  newVisitis: {
    expectedData: [100, 120, 161, 134, 105, 160, 165],
    actualData: [120, 150, 181, 154, 135, 190, 185],
    xxxxData: [0, 60, 81, 74, 55, 80, 85]
  }
}

export default {
  name: 'DashboardAdmin',
  components: {
    LineChart
  },
  data() {
    return {
      lineChartData: lineChartData.newVisitis
    }
  },
  methods: {
    handleSetLineChartData(type) {
      this.lineChartData = lineChartData[type]
    }
  }
}
</script>

<style lang="scss" scoped>
.dashboard-editor-container {
  padding: 10px;
  background-color: rgb(240, 242, 245);
  position: relative;

  .github-corner {
    position: absolute;
    top: 0px;
    border: 0;
    right: 0;
  }

  .chart-wrapper {
    background: #fff;
    padding: 16px 16px 0;
    margin-bottom: 32px;
  }
}

@media (max-width:1024px) {
  .chart-wrapper {
    padding: 8px;
  }
}
</style>
