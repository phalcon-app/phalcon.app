<template>
  <Layout>
    <div class="project">

      <div class="container">

        <div class="project-header">
          <h1 class="project-title" v-html="$page.post.title" />
          <p class="project-sub-title" v-html="$page.post.sub_title" />
        </div>

        <g-image class="project-image" :src="$page.post.image" />

        <JournalContent :content="$page.post.content" />

      </div>

    </div>
  </Layout>
</template>

<page-query>
query ProjectPost ($path: String!) {
  post: projectPost (path: $path) {
    title
    sub_title
    content
    thumbnail
    image (width: 1024, height: 768, quality: 100)
    project_bg_color
    project_fg_color
  }
}
</page-query>

<script>
import JournalContent from "@/components/JournalContent"

export default {
  components: {
    JournalContent
  },

  metaInfo () {
    return {
      title: this.$page.post.title,
      bodyAttrs: {
        style: `background-color: ${this.$page.post.project_bg_color ? this.$page.post.project_bg_color : 'var(--color-base)'};`
                + `color: ${this.$page.post.project_fg_color ? this.$page.post.project_fg_color : 'var(--color-contrast)'}`
      }
    }
  }
}
</script>

<style scoped>
.project-header {
  padding: 20vh 0 0 0;
}
.project-title {
  font-size: 4rem;
  margin: 0;
  padding: 0;
}
.project-sub-title {
  font-size: 1.5rem;
  max-width: 600px;
  margin-top: 1rem;
  margin-bottom: 0;
}
.project-image {
  line-height: 1;
  margin: 8vh 0 3vh;
}
</style>
