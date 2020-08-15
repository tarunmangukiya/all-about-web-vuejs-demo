<template>
  <div>
    <nav-bar />
    <div class="container mt-5">
      <ul v-if="!$fetchState.pending" class="list-unstyled row">
        <li v-for="(item, index) in items.data" :key="index" class="col-3 mb-4">
          <icon-template :item="item" />
        </li>
      </ul>
      <h4 v-else>Loading...</h4>
    </div>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import IconTemplate from '@/components/IconTemplate.vue'

export default {
  components: {
    NavBar,
    IconTemplate
  },

  data() {
    return {
      items: {}
    }
  },

  watch: {
    '$route.query': '$fetch'
  },

  async fetch() {
    const response = await this.$axios.get(`https://api.iconscout.com/v2/search?query=${this.$route.query.q}`)
    this.items = response.data.response.items
  }
}
</script>