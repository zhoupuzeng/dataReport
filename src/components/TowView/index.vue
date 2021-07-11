<template>
  <div>
    <el-row :gutter="20">
      <el-col :span="6">
        <el-card shadow="hover">
          <sale-total />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          鼠标悬浮时显示
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          鼠标悬浮时显示
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          鼠标悬浮时显示
        </el-card>
      </el-col>

    </el-row>
  </div>
</template>
<script>
import SaleTotal from "../SaleTotal/index"
export default {
  name: '',
  components: {
    SaleTotal
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
