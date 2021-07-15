<template>
  <div>
    <el-row :gutter="20">
      <el-col :span="6">
        <el-card shadow="hover">
          <total-sales />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <total-orders />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <today-users />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <total-users />
        </el-card>
      </el-col>

    </el-row>
  </div>
</template>
<script>
import TotalSales from "../TotalSales/index"
import TotalOrders from "../TotalOrders/index"
import TodayUsers from "../TodayUsers/index"
import TotalUsers from "../TotalUsers/index"
export default {
  name: '',
  components: {
    TotalSales,
    TotalOrders,
    TodayUsers,
    TotalUsers
  },
  data () {
    return {
    }
  },
  created () {
  },
  computed: {
  },
  methods: {
  },
}
</script>
<style lang="scss" scoped>

</style>
