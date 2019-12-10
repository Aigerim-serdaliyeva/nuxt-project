<template>
  <el-container>
    <el-header>
      <Navbar />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer></el-footer>
  </el-container>
</template>

<script>
import Navbar from '../components/main/Navbar.vue'
export default {
  components: {
    Navbar

  }
}
</script>

<style>

</style>
