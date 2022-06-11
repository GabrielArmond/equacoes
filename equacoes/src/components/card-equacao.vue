<template>
  <v-container fluid>
    <v-row>
      <v-col
        align-self="start"
        v-for="(equacao, i) in equacoes"
        :key="i"
        :md="equacao.flex"
        sm="12"
      >
        <v-card outlined class="mx-auto" max-width="500">
          <v-row class="pa-5">
            <v-col>
              <v-img class="img" :src="equacao.src"></v-img>
            </v-col>
          </v-row>

          <v-row>
            <v-col md="12" sm="12" class="pt-0">
              <div>
                <v-card-title class="pt-0" style="justify-content: center">
                  {{ equacao.descricao }}
                </v-card-title>
              </div>
              <div class="text-center">
                <v-card-subtitle>
                  {{ equacao.formula }}
                </v-card-subtitle>
              </div>
            </v-col>
          </v-row>

          <v-card-actions class="text-center">
            <v-row>
              <v-col md="12" sm="12">
                <v-btn color="green" dark @click="abrirDialog(equacao)">
                  Calcular
                </v-btn>
              </v-col>
            </v-row>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'CardEquacao',
  emits: ['abrirDialog'],
  data: () => ({
    equacoes: [
      {
        id: 0,
        descricao: 'Equação para diâmetro do parafuso',
        src: require('@/assets/imagens/formula-diametro-arruela.png'),
        formula: 'd = √4/π×(P/σ_adm )',
        flex: 6
      },
      {
        id: 1,
        descricao: 'Equação para espessura do teto',
        src: require('@/assets/imagens/formula-espessura-teto.png'),
        formula: 'h = 1/(π × d_arruela) × (P/τ_adm )',
        flex: 6
      }
    ]
  }),
  methods: {
    abrirDialog(equacao) {
      this.$emit('abrirDialog', equacao)
    }
  }
}
</script>

<style lang="scss">
.img {
  margin-left: auto;
  margin-right: auto;
  width: 250px;
  height: 100%;
}
</style>
