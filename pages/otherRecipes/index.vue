<template>
    <div class="recipes">
        <!-- <p>Not Already</p> -->
        <ul>
            <li v-for="content in contents" :key="content.id">
                <nuxt-link :to="`/${content.id}`">
                    {{ content.title }}
                </nuxt-link>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.recipes {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>

<script>
import axios from 'axios'

export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://nuxt-sample.microcms.io/api/v1/news',
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { 
            'X-API-KEY': 'a6728b4b-f4f3-49f1-bee3-c113e9327a63' 
        }
      }
    )
    return data
  }
}
</script>
