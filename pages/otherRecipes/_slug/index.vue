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
  async asyncData({ $config, params }) {
    const { data } = await axios.get(
      process.env.baseUrl + '/api/v1/articles/' + params.slug,
      {
        headers: {
            'X-API-KEY': $config.apiKey
            // 'a6728b4b-f4f3-49f1-bee3-c113e9327a63' 
        }
      }
    )
    return data
  }
}
</script>
