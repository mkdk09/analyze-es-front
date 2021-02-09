<template>
  <div>
    <v-app-bar
      color="gray accent-4"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title class="mx-1 px-1">ANALYZEES</v-toolbar-title>
      <!-- <router-link to="/">Analyzees</router-link> -->
      <!-- <router-link to="/analyze">Go to analyze</router-link> -->
      <!-- <div class="flex-grow-1"></div> -->
      <v-btn text to="/" class="mx-1 px-1"><v-icon>mdi-home</v-icon>Home</v-btn>
      <v-btn text to="/analyze" class="mx-1 px-1"><v-icon>mdi-file-chart</v-icon>Analyze</v-btn>
      <!-- <v-btn icon>
        <v-icon>mdi-home</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-file-chart</v-icon>
      </v-btn> -->
      <!-- <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            @click="() => {}"
          >
            <v-list-item-title>りんく {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu> -->
    </v-app-bar>
  </div>
</template>
