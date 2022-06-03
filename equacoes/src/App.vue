<template>
  <v-app>
    <v-main class="blue-grey lighten-5">
      <AppBar />
      <v-row no-gutters align="center">
        <v-col>
          <Home />
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import Home from '@/views/home-equation.vue'
import AppBar from '@/components/app-bar.vue'

export default {
  name: 'App',
  components: {
    Home,
    AppBar
  },

  data: () => ({})
}
</script>

<style lang="scss">
.size {
  max-width: 1280px;
  min-width: none;
  height: 100%;
}
</style>
