<template>
  <div>
    <b-card
      :title="item.name"
      :img-src="item.urls.png_256"
      :img-alt="item.name"
      img-top
      tag="article"
    >
      <b-button variant="primary" @click="show = true">View Details</b-button>
    </b-card>

    <b-modal v-model="show" :title="item.name">
      <img :src="item.urls.png_256" class="d-block mx-auto mb-4" width="256" />
      <h5>Price: ${{ item.licenses[0].price }}</h5>
      <h5>License:</h5>
      <h6>{{ item.licenses[0].name }}</h6>
      <p>{{ item.licenses[0].description }}</p>
    </b-modal>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      default: () => ({})
    }
  },

  data() {
    return {
      show: false
    }
  }
}
</script>