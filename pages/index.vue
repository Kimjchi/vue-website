<template>
  <v-container fluid>
    <v-container style="padding: 10% 0">
      <h1 style="font-size: 3em;" class="text-center">Jérémy Kim is a lazy, trying to be creative, French Full Stack Developer based (currently) in Paris.</h1>
    </v-container>
    <v-container>
      <v-row>
        <v-col
          v-for="n in items"
          :key="n.pathLong"
          cols="12" lg="6"
        >
          <img :src="n.pathLong" style="max-height: 100%; max-width: 100%"/>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      items: []
    }
  },

  mounted() {
    this.importAll(require.context('../assets/photos/', false, /\.(jpg|JPG)$/));
  },

  methods: {
    importAll(r) {
      r.keys().reverse().forEach(key => (this.items.push({ pathLong: r(key), pathShort: key })));
    },
  },
}
</script>
