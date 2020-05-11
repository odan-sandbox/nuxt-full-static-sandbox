<template>
  <div class="container">
    <div>data: {{ url }}</div>
    <nuxt-link to="/about">
      abount
    </nuxt-link>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  async asyncData ({ app }) {
    const response = await app.$axios.get('https://httpbin.org/get')
    return {
      url: response.data.url
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
