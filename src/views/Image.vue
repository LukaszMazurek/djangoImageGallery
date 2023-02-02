<template>
  <div class="page-images">
    <div class="columns is-multiline">
      <div class="column is-9">
        <figure class="image mb-6">
          <img v-bind:src="image.get_image">
        </figure>
        <h1 class="title">{{image.name}}</h1>
        <p>{{image.description}}</p>
        <div class="column is-3">
          <h2 class="subtitle">Information</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import axios from "axios";

export default {
  name: 'Image',
  data() {
    return {
      image: {},
      quantity: 1
    }
  },
  mounted() {
    this.getImage()
  },
  methods: {
    getImage(){
      const category_slug = this.$route.params.category_slug
      const image_slug = this.$route.params.image_slug

      axios
        .get(`/api/v1/images/${category_slug}/${image_slug}`)
        .then(response => {
          this.image = response.data
        })
      .catch(error =>
          console.log(error)
      )
    }
  }
}
</script>