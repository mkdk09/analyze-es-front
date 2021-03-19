<template>
  <div>
    <v-app-bar
      color="gray accent-4"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title class="mx-1 px-1">
        ANALYZEES
      </v-toolbar-title>

      <v-btn text to="/" class="mx-1 px-1">
        <v-icon>
          mdi-home
        </v-icon>
        Home
      </v-btn>

      <v-btn text to="/analyze" class="mx-1 px-1">
        <v-icon>
          mdi-file-chart
        </v-icon>
        Analyze
      </v-btn>
    </v-app-bar>
  </div>
</template>
