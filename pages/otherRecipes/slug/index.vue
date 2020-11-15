<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      'https://nuxt-sample.microcms.io/api/v1/news/${params.slug}',
      {
        headers: { 
            'X-API-KEY': 'a6728b4b-f4f3-49f1-bee3-c113e9327a63' 
        }
      }
    )
    return data
  }
}
</script>
