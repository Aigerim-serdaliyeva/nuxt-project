<template>
  <article class="post">
    <header class="post__header">
      <div class="post__title">
        <h1>Post title</h1>
        <nuxt-link to="/">
          <i class="el-icon-back"></i>
        </nuxt-link>
      </div>
      <div class="post__info">
        <small>
          <i class="el-icon-time"></i>
          {{ new Date().toLocaleString() }}
        </small>
        <small>
          <i class="el-icon-view"></i>
          42
        </small>
      </div>
      <div class="post__img">
        <img src="https://www.socialmediaexaminer.com/wp-content/uploads/2015/09/ig-improve-facebook-posts-480.png" alt="" class="post__img">
      </div>
    </header>
    <main class="post__content">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam error facilis magni nemo, tempore eligendi aperiam velit non officia aliquam.</p>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam error facilis magni nemo, tempore eligendi aperiam velit non officia aliquam.</p>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam error facilis magni nemo, tempore eligendi aperiam velit non officia aliquam.</p>
    </main>
    <footer>
      <CommentForm
        v-if="canAddComment"
        @created="createCommentHandler"
      />
      <div class="comments" v-if="true">
        <Comment
          v-for="comment in 3"
          :key="comment"
        />
      </div>
      <div class="text-center" v-else>
        <h3>Комментариев нет</h3>
      </div>
    </footer>
  </article>
</template>

<script>
import CommentForm from '../../components/main/CommentForm.vue'
import Comment from '../../components/main/Comment.vue'
export default {
  // head() {
  //   return {
  //     title: `${this.post.title} | ${process.env.appname}`,
  //     meta: [
  //       {hid: `post-${this.post._id}`, name: 'description', content: this.post.title},
  //       {hid: `post-${this.post._id}`, name: 'keywords', content: 'post, javascript'},
  //     ]
  //   }
  // },
  components: {
    Comment,
    CommentForm
  },
  data() {
    return {
      canAddComment: true
    }
  },
  methods: {
    createCommentHandler() {
      this.canAddComment = false
    }
  }
}
</script>

<style lang="scss" scoped>
  .post {
    max-width: 600px;
    width: 100%;
    margin: 0 auto;
    &__title {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 1rem;
    }
    &__info {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.5rem;
    }
    &__img {
      width: 100%;
      height: auto;
    }
    &__header {
      margin-bottom: 1.5rem;
    }
    &__content {
      margin-bottom: 2rem;
    }
  }
</style>
