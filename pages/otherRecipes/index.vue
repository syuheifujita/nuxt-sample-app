<template>
  <div>
    <ul>
      <li v-for="content in contents" :key="content.id">
          <nuxt-link :to="`/otherRecipes` + `/${content.id}`">
              {{ content.title }}
          </nuxt-link>
      </li>
    </ul>
  </div>
    <!-- <div class="recipes"> -->
        <!-- <p>Not Already</p> -->
        
    <!-- </div> -->
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
  async asyncData({$config}) {
    const { data } = await axios.get(
      'https://nuxt-sample.microcms.io/api/v1/news',
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    return data
  }
}
</script>
