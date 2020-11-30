<template lang="pug">
<<<<<<< HEAD
  ul.flex
    li.p-4(
      v-for="content in contents"
      :key="content.id")
      p(v-text="$dayjs(content.date).fromNow()")
      nuxt-link(:to="`/${content.id}`") {{ content.title }}
</template>

<script>
import axios from 'axios'
=======
  .container
    div
      logo
      h1.title microcms-nuxt-jamstack-blog
</template>

<script>
export default {}
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
>>>>>>> 489aa993317b986dcc2a106af4ab37d41b544044

export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://hdyk1119.microcms.io/api/v1/blog',
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { 'X-API-KEY': 'c5a388af-bbc9-4a35-9b4d-647b8615c4d8' }
      }
    )
    return data
  }
}
</script>

<style lang="scss">
</style>
