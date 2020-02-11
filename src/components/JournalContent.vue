<template>
    <div 
        class="journal-content"
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
p {
    font-size: 1rem;
    line-height: 1.7;
    margin: 2em 0;
}
h2, h3, h4, h5 , h6 {
    line-height: 1.3;
    margin: 2em 0;
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
    margin-top: -2em;
}
h2 + p,
h3 + p,
h4 + p,
h5 + p,
h6 + p {
    margin-top: -1em;
}
</style>
