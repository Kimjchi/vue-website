<template>
  <v-container fluid>
    <v-container style="padding: 5% 0">
      <h1 style="font-size: 3em;" class="text-center">Reach out, if you wanna talk or whatever.</h1>
    </v-container>
    <v-container>
      <v-row style="margin: auto" justify="center">
        <v-col
          v-for="n in items"
          :key="n.url"
          cols="2"
        >
          <a :href="n.url" target="_blank"><img :src="n.path" style="max-height: 100%; max-width: 100%"/></a>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" class="text-center" style="font-size: 0.8em">
          Icons made by <a href="https://www.flaticon.com/authors/pixel-perfect" title="Pixel perfect" target="_blank">Pixel perfect</a> from <a target="_blank" href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          {
            path: require('~/assets/icons/instagram.svg'),
            url: 'https://www.instagram.com/kimjchi/'
          },
          {
            path: require('~/assets/icons/twitter.svg'),
            url: 'https://twitter.com/kim_jerere'
          },
          {
            path: require('~/assets/icons/facebook.svg'),
            url: 'https://www.facebook.com/jeremy.kim.503645'
          },
          {
            path: require('~/assets/icons/linkedin.svg'),
            url: 'https://www.linkedin.com/in/j%C3%A9r%C3%A9my-v-kim/'
          },
          {
            path: require('~/assets/icons/github.svg'),
            url: 'https://github.com/Kimjchi'
          },
        ]
      }
    }
  }
</script>

<style scoped>
  img {
    opacity: 0.38;
  }
  img:hover {
    opacity: 1;
  }
</style>
