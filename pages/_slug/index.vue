<template lang="pug">
  main.main
    h1.title {{ title }}
    p(v-text="$dayjs(date).fromNow()")
    p.category {{ category && category.name }}
    .post(v-html="$md.render(body)")
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://hdyk1119.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers: { 'X-API-KEY': 'c5a388af-bbc9-4a35-9b4d-647b8615c4d8' }
      }
    )
    return data
  }
}
</script>

<style lang="scss">
.post > * + * {
  margin-top: 2em;
}
</style>
