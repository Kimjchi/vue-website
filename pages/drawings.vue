<template>
  <v-container fluid>
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
    this.importAll(require.context('../assets/images/', false, /\.jpeg$/));

  },

  methods: {
    importAll(r) {
      r.keys().reverse().forEach(key => (this.items.push({ pathLong: r(key), pathShort: key })));
    },
  },
}
</script>
