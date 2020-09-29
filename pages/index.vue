<template>
  <section class="container">
    <MainImage />
    <h1>Alcohol</h1>
  </section>
</template>

<script>
import MainImage from '@/components/MainImage'

export default {
    components: {
        MainImage
    }
}
</script>

<style scoped>
h1 {
  font-size: 80px;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-flow: column;
    padding: 30px;
}
</style>
