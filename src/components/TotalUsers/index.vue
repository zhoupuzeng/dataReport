<template>
  <div>
    <common-card title="累计用户数"
                 value="1,064,553">
      <template>
        <v-chart :option="getOptions()" />
      </template>
      <template v-slot:footer>
        <div class="total-users-footer">
          <span>日同比</span>
          <span class="emphasis">6.36%</span>
          <div class="increase"></div>
          <span class="month">月同比</span>
          <span class="emphasis">32.95%</span>
          <div class="decrease"></div>
        </div>
      </template>
    </common-card>
  </div>
</template>
<script>
// mixins的公共card
import commonCardMixin from "../../mixins/commonCardMixin"
export default {
  name: 'total-users',
  mixins: [commonCardMixin],
  data () {
    return {
      svgdog: 'M 157.72 263.89 h 64.66 l 21.73 -22.69 s 9.27 -12.78 23.01 -15.02 h 19.49 s -0.32 -65.83 12.14 -54.01 c 0 0 6.39 4.79 12.46 39.31 c 0 0 10.55 -36.11 15.02 -22.69 l 5.11 35.79 s 66.79 88.2 82.77 115.05 c 0 0 8.31 22.37 53.69 31 c 0 0 27.48 7.67 65.51 11.82 l 186.31 2.88 s 12.46 -1.6 42.5 24.61 c 0 0 31.96 -3.83 31.96 -36.75 c 0 0 -2.88 -62.32 -35.47 -49.21 c 0 0 -57.52 34.19 -70.63 19.49 c 0 0 -30.36 -37.39 14.06 -54.65 c 0 0 26.21 -6.22 97.47 1.53 c 0 0 41.55 -0.89 54.97 62.71 c 0 0 20.77 69.67 -57.52 100.99 l 17.58 44.1 s 5.43 14.38 2.24 39.63 c 0 0 -2.88 23.97 0 32.92 c 0 0 4.79 18.22 2.88 76.06 c 0 0 1.28 18.54 11.19 27.8 c 0 0 11.19 2.24 14.38 42.18 l 4.47 40.59 s 7.35 39.95 -17.58 43.78 c 0 0 -28.76 7.99 -26.21 -22.37 c 0 0 4.47 -19.17 5.75 -22.69 c 0 0 4.47 -20.13 -2.88 -31.32 c 0 0 -55.29 -80.53 -65.19 -98.43 c 0 0 -2.24 19.49 0.64 31 c 0 0 20.13 27.8 10.23 51.45 c 0 0 -6.07 16.3 -6.71 28.76 c 0 0 -5.43 45.7 -36.11 46.34 c 0 0 -14.7 1.92 -13.42 -22.37 c 0 0 1.6 -14.38 15.98 -39.95 c 0 0 4.79 -18.54 -2.56 -30.36 c 0 0 -44.42 -54.33 -54.65 -76.38 c 0 0 -8.63 -16.3 -11.5 -27.8 c 0 0 -9.27 -22.05 -28.44 -14.7 s -82.94 31.64 -109.7 33.24 c 0 0 -43.7 1.92 -47.21 -0.64 c 0 0 -9.91 -0.32 -7.99 27.8 c 0 0 3.52 95.23 1.6 134.86 c 0 0 -0.96 44.1 -30.04 45.7 c 0 0 -14.7 0.96 -18.86 -15.66 c 0 0 -0.32 -37.07 1.28 -49.21 l -2.88 -0.32 s 0 53.37 -20.45 57.84 c 0 0 -18.86 4.79 -17.26 -19.49 c 0 0 5.11 -80.53 1.6 -118.88 c 0 0 -0.64 -25.89 -14.7 -36.11 c 0 0 -61.36 -68.07 -65.19 -98.43 l 0.64 -38.03 s 1.28 -9.59 -11.82 -21.41 c 0 0 -25.25 -18.54 -25.89 -46.66 l -0.96 -40.59 s -0.96 -20.77 -20.45 -23.97 c 0 0 -45.7 -3.2 -59.12 -14.7 c 0 0 -16.3 -14.38 -5.11 -21.09 c 0 0 6.07 -4.79 24.61 -6.39 l -31.42 -19.81 s -15.23 -13.1 -12.36 -28.44 c -0.01 -0.02 0.1 -8.01 12.35 -8.01 Z'
    }
  },
  mounted () {
  },
  computed: {
  },
  methods: {
    getOptions () {
      return {
        xAxis: {
          type: 'value',
          show: false,
        },
        yAxis: {
          type: 'category',
          show: false
        },
        series: [{
          color: '#45c946',
          type: 'bar',
          data: [200],
          barWidth: 10,
          stack: '总量',
        }, {
          color: '#ccc',
          type: 'bar',
          data: [250],
          stack: '总量',
        }, {
          type: 'custom',
          data: [200],
          stack: '总量',
          renderItem: (params, api) => {
            const value = api.value(0);
            const endPoint = api.coord([value, 0]);
            return {
              type: 'group',
              position: endPoint,
              children: [
                {
                  type: 'path',
                  shape: {
                    d: this.svgdog,
                    x: 0,
                    y: -25,
                    width: 20,
                    height: 20,
                    layout: 'cover'
                  },
                  style: {
                    fill: '#45c946'
                  }
                },
                {
                  type: 'path',
                  shape: {
                    d: this.svgdog,
                    x: 0,
                    y: 5,
                    width: 20,
                    height: 20,
                    layout: 'cover'
                  },
                  style: {
                    fill: 'orange'
                  }
                }
              ]

            }
          }
        },],
        grid: {
          top: 0,
          bottom: 0,
          left: 0,
          right: 0
        }
      }
    }
  },
}
</script>
<style lang="scss" scoped>
.total-users-footer{
  display: flex;
  align-items: center;
  .month{
    margin-left: 10px;
  }
}
</style>

