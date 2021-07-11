<template>
  <div class="common-card">
    <div class="title"
         :title="title">{{title}}</div>
    <div class="value"
         :value="value">{{value}}</div>
    <div class="chart">
      <slot></slot>
    </div>
    <div class="line"></div>
    <div class="total">
      <slot name="footer"></slot>
    </div>
  </div>
</template>
<script>
export default {
  name: "commoncard",
  props: {
    title: String,
    value: String,
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
.title {
  font-size: 12px;
  color: #999;
}
.value {
  font-size: 25px;
  color: #000;
  margin-top: 5px;
  letter-spacing: 1px;
}
</style>
