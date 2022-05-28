<template>
  <v-app>
    <v-main>
      <Home />
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

<style lang="scss"></style>
