<template>
  <v-app :style="{ background: $vuetify.theme.themes.light.background }">
    <Header/>
    <router-view/>
    <!-- <router-link to="/">Go to top</router-link>
    <router-link to="/analyze">Go to analyze</router-link> -->
  </v-app>
</template>

<script>
import Header from './components/Header'

export default {
  components: {
    Header
  }
}
</script>
