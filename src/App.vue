<template>
  <v-app>
    <v-main>
      <v-row>
        <v-col md="2" sm="12" class="pa-0">
          <NavBar style="width: 100%" />
        </v-col>

        <v-col align="center" md="10" sm="12" class="pt-12">
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

<style lang="scss"></style>
