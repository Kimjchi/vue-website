<template>
  <v-app>
    <v-container v-if="error.statusCode === 404" class="text-center">
      <img :src="illustration" style="max-height: 90%; max-width: 90%"/>
      <h1 style="margin-top: 2%">{{ pageNotFound }}</h1>
    </v-container>
    <h1 v-else class="text-center">
      {{ otherError }}
    </h1>
  </v-app>
</template>

<script>
export default {
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  head () {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  },
  data () {
    return {
      pageNotFound: `The page ${$nuxt.$route.path} is still under construction. Check it out later :D`,
      otherError: 'An error occurred',
      illustration: require('~/assets/icons/under_construction.svg')
    }
  },
  updated() {
    this.pageNotFound = `The page ${$nuxt.$route.path} is still under construction. Check it out later :D`;
  }
}
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>
