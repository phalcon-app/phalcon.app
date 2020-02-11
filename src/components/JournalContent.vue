<template>
    <div 
        class="post-content"
        v-html="content"
    />
</template>

<script>
export default {
    props: {
        content: String
    }
}
</script>

<style>
.post-content {
  max-width: 600px;
}
p {
    font-size: 1rem;
    line-height: 1.7;
    margin: 2em 0;
}
h2, h3, h4, h5 , h6 {
    line-height: 1.3;
    margin: 2rem 0;
}
h2 {
    font-size: 2rem;
}
h3 {
    font-size: 1.5rem;
}
h4, h5, h6 {
    font-size: 1.15rem;
}
h2 + h3,
h3 + h4,
h4 + h5,
h5 + h6 {
    margin-top: -1rem;
}
h2 + p, h3 + p, h4 + p, h5 + p, h6 + p,
h2 + ul, h3 + ul, h4 + ul, h5 + ul, h6 + ul,
h2 + ol, h3 + ol, h4 + ol, h5 + ol, h6 + ol {
    margin-top: -1rem;
}
p + h2, p + h3, p + h4, p + h5, p + h6,
ul + h2, ul + h3, ul + h4, ul + h5, ul + h6,
ol + h2, ol + h3, ol + h4, ol + h5, ol + h6{
    margin-top: 3rem;
}
</style>
