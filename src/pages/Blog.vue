<template>
  <Layout>

    <div class="container">
      <div class="journal-hero">
        <h1 class="journal-header">
          Our blog...
        </h1>
      </div>
    </div>

    <g-link :to="item.node.path" v-for="item in $page.posts.edges" :key="item.node.id" class="journal-post">
      <div class="container journal">

        <g-image class="journal-image" :src="item.node.image" />
        <h2 class="journal-title">{{ item.node.title }}</h2>
        <p class="journal-excerpt">{{ item.node.excerpt }}</p>

      </div>
    </g-link>
      
  </Layout>
</template>

<page-query>
query Journal {
	posts: allJournalPost {
    edges {
      node {
        id
        path
        title
        image (width: 768, height: 768, quality: 100)
        excerpt
      }
    }
  }
}
</page-query>

<script>
export default {
}
</script>

<style scoped>
.container.journal {
  max-width: 920px;
}
.journal-hero {
  padding: 4rem 0;
  text-align: center;
  color: var(--color-base-1);
}
.journal-header {
  font-size: 3rem;
  font-weight: 700;
  padding: 0;
  margin: 0;
}

.journal-post {
  display: block;
  padding: 2rem 0;
  text-decoration: none;
  transition: background 0.5s ease;
}
.journal-post > * {
  transition: transform 0.5s ease;
}
.journal-post:hover {
  background-color: var(--color-base-1);
}
.journal-image {
  float: left;
  width: 100%;
  margin: 0 0 20px;
}
.journal-title {
  font-size: 2rem;
  color: var(--color-contrast);
  margin: 0 0 2rem 0;
  padding: 0;
}
.journal-excerpt {
  color: var(--color-contrast-1);
}

@media (min-width: 560px) {
  .journal-image {
    float: left;
    width: 140px;
    margin: 0 50px 0 0;
  }
  .journal-post {
    padding: 3rem 0;
  }
}

@media (min-width: 860px) {
  .journal-post {
    padding: 5rem 0;
  }
}
</style>
