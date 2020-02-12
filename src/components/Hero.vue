<template>
    <div class="hero">
        <h1 class="hero-title" v-html="settings.hero_title" />
        <p class="hero-subtitle" v-html="settings.hero_subtitle" />
    </div>
</template>

<script>
export default {
  data() {
    return {
      settings: require("../../data/settings.json")
    }
  }
}
</script>

<style>
.hero {
    text-align: left;
    width: 600px;
    max-width: 100%;
    margin: 0;
    padding: 4rem 0 6rem 0;
}

.hero-title {
    font-size: 4rem;
    margin: 0;
    padding: 0;
}
.hero-title p,
.hero-subtitle p {
    margin: 0;
    padding: 0;
}
.hero-subtitle {
    font-size: 1.5rem;
    font-weight: 400;
    line-height: 1.68;
    padding: 0;
    margin: 1rem auto 0;
    color: #666;
}
</style>
