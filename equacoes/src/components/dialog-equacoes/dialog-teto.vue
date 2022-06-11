<template>
  <v-card class="overflow-x-hidden">
    <v-toolbar dark>
      {{ titulo }}
      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon dark @click="fecharDialog">mdi-close</v-icon>
      </v-btn>
    </v-toolbar>
    <v-row align="center">
      <v-col class="text-center">
        <h3 class="pt-5">h = 1/(π × d_parafuso) × (P/τ_adm )</h3></v-col
      >
    </v-row>
    <v-card-text>
      <div class="text-h2 pa-12">
        <v-row>
          <v-col md="6" sm="12">
            <v-text-field
              v-model="forca"
              label="Força"
              hint="Digite a força em Kilo Newton"
              suffix="N"
              persistent-hint
              filled
              dense
            ></v-text-field>
          </v-col>
          <v-col md="6" sm="12">
            <v-text-field
              v-model="diametroArruela"
              label="Diâmetro da arruela"
              hint="Digite o diâmetro da arruela em milimetro"
              suffix="mm"
              persistent-hint
              filled
              dense
            ></v-text-field>
          </v-col>
          <v-col md="12" sm="12">
            <v-text-field
              v-model="tensaoCisalhamento"
              label="Tensão de cisalhamento do material (teto)"
              hint="Digite a tensão de cisalhamento em Kilo Pascal"
              suffix="Pa"
              persistent-hint
              filled
              dense
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row justify="center">
          <v-col cols="6">
            <v-text-field
              v-model="espessuraTeto"
              label="Espessura teto"
              suffix="mm"
              filled
              dense
              readonly
            ></v-text-field>
          </v-col>
        </v-row>
      </div>
    </v-card-text>
    <v-card-text>
      <v-row class="text-center">
        <v-col md="12" sm="12">
          <span class="text-h6"> Resolução da equação:</span>
          <p>
            {{ espessuraTeto || 'h' }} = 1/(π ×
            {{ diametroArruela || 'd_arruela' }}) × ( {{ forca || 'P' }}/
            {{ tensaoCisalhamento || 'τ_adm' }} )
          </p>
        </v-col>
      </v-row>
    </v-card-text>
    <v-card-actions class="justify-end">
      <v-btn color="error" @click="limparCampos">Limpar campos</v-btn>
      <v-btn color="primary" @click="calcular">Calcular</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: 'DialogParafuso',
  emits: ['close'],
  props: {
    titulo: {
      type: String,
      default: 'Equação'
    }
  },
  data() {
    return {
      forca: null,
      diametroArruela: null,
      tensaoCisalhamento: null,
      espessuraTeto: null
    }
  },
  methods: {
    fecharDialog() {
      this.$emit('close')
    },
    calcular() {
      const forca = this.forca
      const diametroArruela = this.diametroArruela
      const tensaoCisalhamento = this.tensaoCisalhamento
      const espessura =
        (1 / (Math.PI * diametroArruela)) * (forca / tensaoCisalhamento)
      const espessuraMM = (espessura * 1000).toFixed(2)
      this.espessuraTeto = espessuraMM
    },
    limparCampos() {
      this.forca = null
      this.tensaoCisalhamento = null
      this.diametroArruela = null
      this.espessuraTeto = null
    }
  }
}
</script>

<style lang="scss"></style>
