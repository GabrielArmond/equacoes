<template>
  <v-navigation-drawer class="nav-bar pa-5 ma-0" permanent color="#0d3b66">
    <v-list>
      <v-list-item class="px-2">
        <v-list-item-avatar>
          <v-img src="../assets/imagens/resistencia.png"></v-img>
        </v-list-item-avatar>
        <v-list-item-title class="text-h6 text-center" style="color: #fff">
          <span>Resistência</span>
          <p>dos materiais</p>
        </v-list-item-title>
      </v-list-item>
    </v-list>

    <v-divider></v-divider>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
.nav-bar {
  height: 100vh;
  text-align: center;
}
</style>
