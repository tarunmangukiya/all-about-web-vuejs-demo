<template>
  <div class="container">
    <ul class="list-unstyled row">
      <li v-for="(item, index) in items.data" :key="index" class="col-3 mb-4">
        <b-card
          :title="item.name"
          :img-src="item.urls.png_256"
          :img-alt="item.name"
          img-top
          tag="article"
        >
          <b-button href="#" variant="primary">View Details</b-button>
        </b-card>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
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