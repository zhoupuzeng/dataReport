<template>
  <div class="sales-view">
    <el-card>
      <template v-slot:header>
        <div class="menu-wrapper">
          <el-menu mode="horizontal"
                   :default-active="activeIndex"
                   @select="onMenuSelect"
                   class="sales-menu">
            <el-menu-item index="1">销售额</el-menu-item>
            <el-menu-item index="2">访问量</el-menu-item>
          </el-menu>
          <div class="menu-right">
            <el-radio-group v-model="radioSelect"
                            size="small">
              <el-radio-button label="今日" />
              <el-radio-button label="本周" />
              <el-radio-button label="本月" />
              <el-radio-button label="今年" />
            </el-radio-group>
            <el-date-picker type="daterange"
                            v-model="date"
                            range-separator="至"
                            start-placeholder="开始日期"
                            end-placeholder="结束日期"
                            size="small"
                            unlink-panels
                            class="sales-date"
                            :picker-options="pickerOptions">

            </el-date-picker>
          </div>
        </div>
      </template>
      <template>11</template>
    </el-card>
  </div>
</template>
<script>
export default {
  data () {
    return {
      activeIndex: '1',
      radioSelect: '今日',
      date: null,
      pickerOptions: {
        shortcuts: [{
          text: '最近一周',
          onClick (picker) {
            const start = new Date();
            const end = new Date();
            start.setTime(start.getTime() - 3600 * 24 * 1000 * 7)
            picker.$emit('pick', [start, end], true)
          }
        }, {
          text: '最近一个月',
          onClick (picker) {
            const start = new Date();
            const end = new Date();
            start.setTime(start.getTime() - 3600 * 24 * 1000 * 30);
            picker.$emit('pick', [start, end], false)
          }
        }, {
          text: '最近三个月',
          onClick (picker) {
            const start = new Date();
            const end = new Date();
            start.setTime(start.getTime() - 3600 * 24 * 1000 * 90);
            picker.$emit('pick', [start, end], false)
          }
        }]
      }
    }
  },
  methods: {
    onMenuSelect (index) {
      this.activeIndex = index
    }
  }
}
</script>
<style lang="scss" scoped>
.sales-view{
  margin-top: 20px;
  .menu-wrapper{
    position: relative;
    display: flex;
    .sales-menu{
      width: 100%;
      padding-left: 20px;
      .el-menu-item{
        height: 50px;
        line-height: 50px;
        margin:  0 20px
      }
    }
    .menu-right{
      position: absolute;
      top: 0;
      right: 20px;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: end;
      .sales-date{
        margin-left: 20px;
      }
    }
  }
}
</style>
