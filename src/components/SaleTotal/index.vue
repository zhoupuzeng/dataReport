<template>
  <div>
    <common-card title="234"
                 value="123">
      <template>
        <div id="charts-sale"
             :style="{width:'100%',height:'100%'}">

        </div>
      </template>
    </common-card>
  </div>
</template>
<script>
import CommonCard from "../CommCard/index"
export default {
  name: '',
  components: {
    CommonCard
  },
  data () {
    return {
    }
  },
  mounted () {
    const chart = this.$echarts.init(document.getElementById("charts-sale"))
    chart.setOption({
      xAxis: {

      },
      yAxis: {},
      series: [{
        type: 'bar',
        data: [1, 2, 3]
      }]
    })
  },
  computed: {
  },
  methods: {
  },
}
</script>
<style lang="scss" scoped>

</style>
