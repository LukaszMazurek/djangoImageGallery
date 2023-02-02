<template>
  <div class="home">
    <section class="hero is-medium is-dark mb-6">
      <div class="hero-body has-text-centered">
        <p class="title mb-6">
          Welcome to ImageGallery
        </p>
      </div>
    </section>

    <div class="columns-is-multiline">
      <div class="column is-12">
        <h2 class="is-size-2 has-text-centered">Latest images</h2>
      </div>

      <div
          class="column is-3"
          v-for="image in latestsImages"
          v-bind:key ="image.id">

        <div class="box">
          <figure class="image mb-4">
            <img :src="image.get_thumbnail">
          </figure>
          <h3 class="is-size-4">{{ image.name }}</h3>

        </div>
        <router-link v-bind:to="image.get_absolute_url" class="button is-dark mt-4">View details</router-link>
      </div>
    </div>
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'HomeView',
  data() {
    return {
      latestsImages: []
    }
  },
  components: {
  },
  mounted() {
    this.getLatestImages()
  },
  methods: {
    getLatestImages(){
      axios
        .get('/api/v1/latests-images/')
        .then(response => {
          this.latestsImages = response.data
        })
      .catch(error => {
        console.log(error)
      })
    }
  }
}
</script>

<style scoped>
  .image {
    margin-top: -1.25rem;
    margin-left: -1.25rem;
    margin-right: -1.25rem;
  }
</style>
