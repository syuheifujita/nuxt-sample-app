<template>
    <section class="recipes">
        <Recipe
            v-for="recipe in recipes"
            :key="recipe.id"
            :id="recipe.id"
            :thumbnail="recipe.thumbnail"
            :title="recipe.title"
            :previewText="recipe.previewText" />
    </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
    components: {
        Recipe
    },
    asyncData() {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: "1",
                            title: "Wine",
                            previewText: "Awsome Alcohol!",
                            thumbnail: "https://www.illust-box.jp/db_img/sozai/00009/96079/watermark.jpg"
                        },
                        {
                            id: "2",
                            title: "Champagne",
                            previewText: "Awsome Alcohol!",
                            thumbnail: "https://www.illust-box.jp/db_img/sozai/00009/95945/watermark.jpg"
                        },
                        {
                            id: "3",
                            title: "Champagne",
                            previewText: "Awsome Alcohol!",
                            thumbnail: "https://www.illust-box.jp/db_img/sozai/00009/95945/watermark.jpg"
                        }
                    ]
                })
            })
        })
    }
}
</script>

<style scoped>
.recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}
</style>
