<template>
    <nuxt-link :to="'recipes/' + id">
        <article class="recipe">
            <div class="thumbnail" :style="{
                    backgroundImage: 'url(' + thumbnail + ')'
            }"></div>
            <h1>{{ title }}</h1>
            <p>{{ previewText }}</p>
        </article>
    </nuxt-link>
</template>

<script>
export default {
    props: ["id", 'thumbnail', 'title', 'previewText']
}
</script>

<style scoped>
h1, p {
    text-decoration: none;
    color: black;
}

.recipe {
    color: royalblue;
    width: 180px;
    height: 300px;
    margin: 64px;
}

.thumbnail {
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 100%;
}
</style>
