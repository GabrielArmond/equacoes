<template>
  <v-app>
    <v-main>
      <v-container class="grey lighten-5 size">
        <v-row no-gutters align="center">
          <v-col>
            <Home />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Home from './views/home/home-equation.vue'
export default {
  name: 'App',
  components: {
    Home
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
