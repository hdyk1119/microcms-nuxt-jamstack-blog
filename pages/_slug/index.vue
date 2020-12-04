<template lang="pug">
  main.main
    h1.title {{ title }}
    p.publishedAt {{ publishedAt }}
    .post(v-html="body")
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://hdyk1119.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers: {'X-API-KEY': 'c5a388af-bbc9-4a35-9b4d-647b8615c4d8'}
      }
    )
    return data
  }
}
</script>
