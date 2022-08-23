<template>
  <div style="text-align: center; margin: 20px">
    <el-pagination background layout="total,prev, pager, next,jumper"
      :total="total"
      :page-size="pageSize"
      :current-page="currentPage"
      @current-change="changePage"
    >
    </el-pagination>
  </div>
</template>

<script>
export default {
  // 准备父传子
  props: {
    // 总条数
    total: {
      type: Number,
      default: 100,
    },
    // 页数
    pageSize: {
      type: Number,
      default: 10,
    },
    // 当前页码
    currentPage: {
      type: Number,
      default: 1,
    },
  },
  // watch: {
  //   currentPage(val) {
  //     console.log("---val--", val);
  //   },
  // },
  methods: {
    // 子传父(Goods)
    changePage(page) {
      this.$emit("changePage", page);
    },
  },
  created() {},
};
</script>

<style>
</style>