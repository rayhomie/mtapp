<template>
  <el-container class="layout-default">
    <el-header style="height:200px">
      <myheader />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer style="height:100%">
      <my-footer />
    </el-footer>
  </el-container>
</template>
<script>
import myheader from "@/components/public/header/index.vue";
import MyFooter from "@/components/public/footer/index.vue";
export default {
  components: {
    myheader,
    MyFooter
  }
};
</script>
<style>
</style>
