<template>
  <section class="container">
    <MainImage />
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
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-flow: column;
    padding: 30px;
}
</style>
