<template>
  <section class="container">
    <div>
      <img class="main-image" :src="images.thumbnail" alt="">
    </div>
  </section>
</template>

<script>
import Header from '@/components/Header'

export default {
  asyncData() {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    images: [
                        {
                            thumbnail: "https://www.illust-box.jp/db_img/sozai/00013/139672/watermark.jpg"
                        }
                    ]
                })
            })
        })
    }
}
</script>

<style scoped>
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-flow: column;
    padding: 30px;
}

.main-image {
    width: 500px;
    height: 300px;
    margin: 32px;
}
</style>
