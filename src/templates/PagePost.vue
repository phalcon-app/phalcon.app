<template>
  <Layout>
    <div class="page">

      <div class="container">

        <div class="page-header">
          <h1 v-html="$page.post.title" class="page-title" />
          <p class="page-sub-title" v-html="$page.post.sub_title" />
        </div>

        <g-image class="page-image" :src="$page.post.image" v-if="showImage" />

        <JournalContent :content="$page.post.content" />

      </div>

    </div>
  </Layout>
</template>

<page-query>
query PagePost ($path: String!) {
  post: pagePost (path: $path) {
    title
    image_hide
    sub_title
    excerpt
    image (width: 1024, height: 768, quality: 100)
    content
  }
}
</page-query>

<script>
import JournalContent from "@/components/JournalContent"

export default {
  components: {
    JournalContent
  },
  computed: {
    showImage: function () {
      return this.$page.post.image_hide != true;
    }
  },
  data() {
    return {
      settings: require("../../data/settings.json")
    }
  },
  metaInfo () {
    return {
      title: `${this.$page.post.title} - ${this.settings.site_name}`
    }
  }
}
</script>

<style scoped>
.page-header {
  padding: 20vh 0 0 0;
}
.page-title {
  font-size: 4rem;
  margin: 0;
  padding: 0;
}
.page-sub-title {
  font-size: 1.5rem;
  max-width: 600px;
  margin-top: 1rem;
  margin-bottom: 0;
}
.page-image {
  line-height: 1;
  margin: 8vh 0 3vh;
}
</style>
