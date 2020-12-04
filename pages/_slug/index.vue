<template lang="pug">
  main.main
    h1.title {{ title }}
<<<<<<< HEAD
    p.publishedAt {{ publishedAt }}
    .post(v-html="body")
=======
    p(v-text="$dayjs(date).fromNow()")
    p.category {{ category && category.name }}
    .post(v-html="$md.render(body)")
>>>>>>> 13cbcc9a17def6e6dca519a3309293f237932820
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://hdyk1119.microcms.io/api/v1/blog/${params.slug}`,
      {
<<<<<<< HEAD
        headers: {'X-API-KEY': 'c5a388af-bbc9-4a35-9b4d-647b8615c4d8'}
=======
        headers: { 'X-API-KEY': 'c5a388af-bbc9-4a35-9b4d-647b8615c4d8' }
>>>>>>> 13cbcc9a17def6e6dca519a3309293f237932820
      }
    )
    return data
  }
}
</script>
<<<<<<< HEAD
=======

<style lang="scss">
.post > * + * {
  margin-top: 2em;
}
</style>
>>>>>>> 13cbcc9a17def6e6dca519a3309293f237932820
