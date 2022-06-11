<template>
  <v-app>
    <v-main>
      <v-row>
        <v-col md="3" sm="12" class="pa-0">
          <NavBar />
        </v-col>

        <v-col align="center" md="8" sm="12" class="pt-12">
          <Home />
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import Home from '@/views/home-equation.vue'
import NavBar from '@/components/nav-bar.vue'

export default {
  name: 'App',
  components: {
    Home,
    NavBar
  },

  data: () => ({})
}
</script>

<style lang="scss">
main {
  overflow: hidden;
}
</style>
