<template>
  <el-row type="flex" justify="center">
    <el-col :xs="20" :sm="16" :md="12" :lg="10">
      <Post
        v-for="post in 3"
        :key="post"
      />
    </el-col>
  </el-row>
</template>

<script>
import Post from '../components/main/Post.vue'

export default {
  components: {
    Post

  }
}
</script>

<style>

</style>
