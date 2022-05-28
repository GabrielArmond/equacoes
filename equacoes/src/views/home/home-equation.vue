<template>
  <v-container class="ma-5 size text-center">
    <v-col cols="12">
      <v-row justify="center">
        <h1>Equações Resistência dos Materiais</h1>
      </v-row>
      <v-row>
        <v-col cols="12">
          <p>
            Este projeto tem o intuito de calcular algumas equações usadas na
            disciplina de Resistência dos materiais.
          </p>
        </v-col>
      </v-row>
      <v-spacer></v-spacer>
      <v-container>
        <v-col>
          <v-row justify="center">
            <p>Escolha abaixo qual tipo de equação queira calcular</p>
          </v-row>
        </v-col>
        <v-container
          fluid
          class="grey lighten-5 container-card"
          style="width: 100%"
        >
          <v-row justify="center">
            <v-col cols="8">
              <v-row>
                <v-card
                  v-for="(equation, i) in equacoes"
                  :key="i"
                  class="mx-auto pa-4 ma-2"
                  max-width="400"
                  outlined
                >
                  <v-list-item>
                    <v-list-item-content>
                      <div class="text-h5 mb-4">
                        {{ equation.descricao }}
                      </div>
                      <v-list-item-title class="text-h6 mb-1">
                        <v-col cols="12">
                          <v-row justify="center" class="pa-2">
                            <v-img max-width="170" :src="equation.imagem" />
                          </v-row>
                          <v-row class="pa-1" justify="center">
                            {{ equation.formula }}
                          </v-row>
                        </v-col>
                      </v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                  <v-col cols="12" md="12" xs="12">
                    <v-row justify="center">
                      <v-card-actions>
                        <v-btn
                          color="primary"
                          width="150"
                          large
                          elevation="4"
                          rounded-sm
                        >
                          Calcular
                        </v-btn>
                      </v-card-actions>
                    </v-row>
                  </v-col>
                </v-card>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-container>
    </v-col>
  </v-container>
</template>

<script>
export default {
  name: 'Home-equation',

  data: () => ({
    equacoes: [
      {
        id: 1,
        descricao: 'Equação para diâmetro do parafuso',
        imagem: require('@/assets/imagens/formula-diametro-arruela.png'),
        formula: 'd = √4/π×(P/σ_adm )'
      },
      {
        id: 2,
        descricao: 'Equação para espessura do teto',
        imagem: require('@/assets/imagens/formula-espessura-teto.png'),
        formula: 'h = 1/(π × d_parafuso) × (P/τ_adm )'
      }
    ]
  })
}
</script>

<style lang="scss">
.size {
  width: 100%;
}
</style>
