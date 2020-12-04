<template lang="pug">
  ul.flex
    li.p-4(
      v-for="content in contents"
      :key="content.id")
      p(v-text="$dayjs(content.date).fromNow()")
      nuxt-link(:to="`/${content.id}`") {{ content.title }}
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      'https://hdyk1119.microcms.io/api/v1/blog',
      {
        headers: {'X-API-KEY': 'c5a388af-bbc9-4a35-9b4d-647b8615c4d8'}
      }
    )
    return data
  }
}
</script>