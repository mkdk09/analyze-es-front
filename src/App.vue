<template>
  <v-app :style="{ background: $vuetify.theme.themes.light.background }">
    <Header/>
    <router-view/>
  </v-app>
</template>

<script>
import Header from '@/components/Header'

export default {
  components: {
    Header
  }
}
</script>
