<template>
    <section class="single-recipe">
        <h1>{{ recipe.title }}</h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
        </div>
        <p>{{ recipe.descriptionText }}</p>
    </section>
</template>

<script>
export default {
    asyncData(context) {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
                        {
                            id: "1",
                            title: "Wine",
                            previewText: "Awsome Alcohol!",
                            descriptionText: "This is really a delicious drink!",
                            thumbnail: "https://www.illust-box.jp/db_img/sozai/00009/96079/watermark.jpg"
                        },
                        {
                            id: "2",
                            title: "Champagne",
                            previewText: "Awsome Alcohol!",
                            descriptionText: "This is really a delicious drink!",
                            thumbnail: "https://www.illust-box.jp/db_img/sozai/00009/95945/watermark.jpg"
                        }
                    ].find(el => el.id === context.params.id)
                })
            })
        })
    }
}
</script>

<style scoped>
.single-recipe {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-flow: column;
    padding: 30px;
}

.recipe-image {
    width: 300px;
    height: 450px;
    margin: 32px;
}

</style>
