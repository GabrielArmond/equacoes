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
          <v-row justify="center">
            <v-col md="12" sm="12">
              <v-img :src="equacao.src"></v-img>
            </v-col>
          </v-row>
          <v-row>
            <v-col md="12" sm="12">
              <v-card-title style="justify-content: center">
                {{ equacao.descricao }}
              </v-card-title>

              <v-card-subtitle>
                {{ equacao.formula }}
              </v-card-subtitle>
            </v-col>
          </v-row>

          <v-card-actions>
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

<style lang="scss"></style>
