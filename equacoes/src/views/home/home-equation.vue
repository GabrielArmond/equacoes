<template>
  <v-container class="ma-5 text-center">
    <v-col cols="12">
      <v-col class="title-style">
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
      </v-col>
      <v-container>
        <v-col>
          <v-row justify="center">
            <p class="pa-3">
              Escolha abaixo qual tipo de equação queira calcular
            </p>
          </v-row>
        </v-col>
        <v-container fluid>
          <v-row dense>
            <v-col
              align-self="start"
              v-for="(equacao, i) in equacoes"
              :key="i"
              :cols="equacao.flex"
            >
              <v-card class="mx-auto" max-width="344">
                <v-img :src="equacao.src"></v-img>

                <v-card-title> {{ equacao.descricao }} </v-card-title>

                <v-card-subtitle> {{ equacao.formula }} </v-card-subtitle>

                <v-card-actions>
                  <v-btn
                    color="primary lighten-2"
                    @click="dialog_parafuso = true"
                  >
                    Calcular
                  </v-btn>
                  <v-spacer></v-spacer>
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-container>
    </v-col>

    <v-dialog
      persistent
      v-model="dialog_parafuso"
      transition="dialog-bottom-transition"
      max-width="600"
    >
      <transition>
        <DialogParafuso
          v-if="dialog_parafuso"
          @close="dialog_parafuso = false"
        />
      </transition>
    </v-dialog>
  </v-container>
</template>

<script>
import DialogParafuso from '../../components/dialog-equacoes/dialog-parafuso.vue'
export default {
  name: 'Home-equation',

  components: {
    DialogParafuso
  },

  data: () => ({
    equacoes: [
      {
        id: 1,
        descricao: 'Equação para diâmetro do parafuso',
        src: require('@/assets/imagens/formula-diametro-arruela.png'),
        formula: 'd = √4/π×(P/σ_adm )',
        flex: 6
      },
      {
        id: 2,
        descricao: 'Equação para espessura do teto',
        src: require('@/assets/imagens/formula-espessura-teto.png'),
        formula: 'h = 1/(π × d_parafuso) × (P/τ_adm )',
        flex: 6
      }
    ],
    dialog_parafuso: false
  })
}
</script>

<style lang="scss">
.title-style {
  font-family: 'Roboto', sans-serif;
  font-weight: 700;
  padding: 10px 10px 10px 0;
  border: 1px solid #e6e6e6;
  border-radius: 10px;
}
</style>
