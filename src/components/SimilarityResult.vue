<template>
  <v-card max-width="450" class="mx-auto">
    <v-toolbar dark>
      <v-toolbar-title>
        Result
      </v-toolbar-title>
    </v-toolbar>

    <v-list three-line>
      <template v-for="(score, item, index) in items">
        <v-list-item :key="item">
          <v-list-item-content>
            <v-list-item-title id="result">
              {{ index + 1 }}位: {{ item }} <br>
              Score: {{ score }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-divider :key="index"></v-divider>
      </template>
    </v-list>
  </v-card>
</template>

<script>
export default {
  name: 'SimilarityResult',
  props: ['items']
}
</script>

<style scoped>
#result {
  color: #555;
  font-family: 'Varela Round', sans-serif;
}
</style>
