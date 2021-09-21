<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      process.env.SERVICE_DOMAIN ,
      {
        headers: { 'X-API-KEY': process.env.API_KEY }
      }
    )
    return data
  }
}
</script>