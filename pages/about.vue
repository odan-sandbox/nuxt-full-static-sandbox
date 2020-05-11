<template>
  <div class="container">
    <div>data: {{ origin }}</div>
    <nuxt-link to="/">
      index
    </nuxt-link>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  async asyncData ({ app }) {
    const response = await app.$axios.get('https://httpbin.org/ip')
    return {
      origin: response.data.origin
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;
}

</style>
