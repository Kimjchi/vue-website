<template>
  <v-app>
    <v-container
      fluid
      class="lighten-5 mb-6"
      style="margin-top: 2%"
    >
      <v-row
        no-gutters
        align="center"
      >
        <v-col
          cols="1"
          class="text-center"
        >
          <nuxt-link v-if="$vuetify.breakpoint.mdAndUp"  to="/">Gallery</nuxt-link>
        </v-col>
        <v-col
          cols="1"
          class="text-center"
        >
          <nuxt-link v-if="$vuetify.breakpoint.mdAndUp"  to="/comics">Comics</nuxt-link>
        </v-col>
        <v-col
          cols="1"
          class="text-center"
        >
          <nuxt-link v-if="$vuetify.breakpoint.mdAndUp"  to="/writing">Writing</nuxt-link>
        </v-col>
        <v-col
          cols="6"
          class="text-center"
        >
            <h1>KIM</h1>
        </v-col>
        <v-spacer />
        <v-col
          cols="1"
          class="text-center"
        >
          <nuxt-link v-if="$vuetify.breakpoint.mdAndUp"  to="/projects">Projects</nuxt-link>
        </v-col>
        <v-col
          cols="1"
          class="text-center"
        >
          <nuxt-link v-if="$vuetify.breakpoint.mdAndUp"  to="/about">About</nuxt-link>
        </v-col>
        <v-col
          cols="1"
          class="text-center"
        >
          <nuxt-link v-if="$vuetify.breakpoint.mdAndUp" to="/contact">Contact</nuxt-link> <v-app-bar-nav-icon v-if="!$vuetify.breakpoint.mdAndUp" @click.stop="drawer = !drawer"/>
        </v-col>
      </v-row>
      <v-navigation-drawer v-model="drawer" enable-resize-watcher light app right>
        <v-icon @click.stop="drawer = !drawer" class="float-right" style="margin-top: 12%; margin-right: 5%">mdi-close</v-icon>
        <v-list
          dense
          nav
          style="margin-top: 50%"
          class="text-center"
        >
          <v-list-item
            v-for="item in items"
            :key="item.title"
            :to="item.to"
            link
          >
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-container>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <v-footer
      app
    >
      <span style="margin: auto">Powered by Jeremy's dumb imagination &copy; 2020</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      items: [
        {
          title: 'Gallery',
          to: '/'
        },
        {
          title: 'Comics',
          to: '/comics'
        },
        {
          title: 'Writing',
          to: '/writing'
        },
        {
          title: 'Projects',
          to: '/projects'
        },
        {
          title: 'About',
          to: '/about'
        },
        {
          title: 'Contact',
          to: '/contact'
        },
      ],
      title: 'KIM'
    }
  },
  mounted() {
    this.drawer = false;
  }
}
</script>

<style scoped>
  .v-application, .v-footer {
    background-color: #FAFAFA;
  }
  .v-application a {
    text-decoration: none;
    opacity: 0.38;
    color: black;
    font-family: Europa, sans-serif;
  }
  .v-application a.nuxt-link-exact-active, a:hover {
    opacity: 1;
  }
</style>
