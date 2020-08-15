<template>
  <div class="container">
    <ul class="list-unstyled row">
      <li v-for="(item, index) in items.data" :key="index" class="col-3 mb-4">
        <icon-template :item="item" />
      </li>
    </ul>
  </div>
</template>

<script>
import IconTemplate from '@/components/IconTemplate.vue'

export default {
  components: {
    IconTemplate
  },

  data() {
    return {
      items: {}
    }
  },

  async fetch() {
    const response = await this.$axios.get('https://api.iconscout.com/v2/search')
    this.items = response.data.response.items
  }
}
</script>