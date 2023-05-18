<template>
  <q-page class="flex flex-center">
   {{ posts }}
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data () {
    return {
      posts: null
    }
  },
  async created () {
    const res = await this.$api.get('/post/v1/2')
    this.post = res.data
  }
})
</script>
