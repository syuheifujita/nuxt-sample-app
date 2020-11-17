<template>
  <div class="articles">
    <!-- <ul>
      <l v-for="content in contents" :key="content.id">
          <nuxt-link :to="`/otherRecipes` + `/${content.id}`">
              <div>
                {{ content.title }}
              </div>
              <div class="post" v-html="content.body"></div>
          </nuxt-link>
      </l>
    </ul> -->
    <div class="article-wrapper">
      <div class="article-box" v-for="content in contents" :key="content.id">
        <nuxt-link :to="`/otherRecipes` + `/${content.id}`">
          <div>
            <img src="
            ../static/favicon.ico" alt="">
          </div>
          <div class="article-title">
            {{ content.title }}
          </div>
          <div class="article-text" v-html="content.body"></div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card-view {
  border: 1px solid;
  display: flex;
  justify-content: center;
  align-items: center;
}

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
      process.env.baseUrl + '/api/v1/articles',
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    return data
  }
}
</script>
