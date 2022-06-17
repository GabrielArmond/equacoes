<template>
  <v-card class="overflow-x-hidden">
    <v-toolbar color="#0d3b66" dark>
      {{ titulo }}
      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon dark @click="fecharDialog">mdi-close</v-icon>
      </v-btn>
    </v-toolbar>
    <v-row align="center">
      <v-col class="text-center">
        <h3 class="pt-5">d = √4/π×(P/σ_adm )</h3></v-col
      >
    </v-row>
    <v-card-text>
      <div class="text-h2 px-2">
        <v-row>
          <v-col cols="12" md="6" sm="12">
            <v-text-field
              v-model="forca"
              label="Força"
              hint="Digite a força em Kilo Newton"
              suffix="kN"
              persistent-hint
              filled
              dense
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="6" sm="12">
            <v-text-field
              v-model="tensaoNormal"
              label="Tensão normal"
              hint="Digite a tensão normal em Kilo Pascal"
              suffix="kPa"
              persistent-hint
              filled
              dense
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="6" sm="12">
            <v-text-field
              v-model="diametroParafuso"
              label="Diâmetro parafuso"
              suffix="mm"
              filled
              dense
              readonly
            ></v-text-field>
          </v-col>
        </v-row>
      </div>
    </v-card-text>
    <v-card-actions class="justify-center pb-5">
      <v-btn color="error" @click="limparCampos">Limpar campos</v-btn>
      <v-btn color="primary" @click="calcular">Calcular</v-btn>
    </v-card-actions>
    <v-card-text>
      <v-row class="text-center">
        <v-col cols="12" md="12" sm="12">
          <span class="text-h6"> Resolução da equação:</span>
          <p>
            {{ diametroParafuso || 'd' }} = √4/π x ({{ forca || 'P' }} /
            {{ tensaoNormal || 'σ_adm' }})
          </p>
        </v-col>
      </v-row>
    </v-card-text>
    <v-divider></v-divider>
    <v-card-text class="pt-5">
      <ResolucaoParafuso />
    </v-card-text>
  </v-card>
</template>

<script>
import ResolucaoParafuso from './resolucao-parafuso.vue'

export default {
  name: 'DialogParafuso',
  emits: ['close'],
  components: { ResolucaoParafuso },
  props: {
    titulo: {
      type: String,
      default: 'Equação'
    }
  },
  data() {
    return {
      forca: null,
      tensaoNormal: null,
      diametroParafuso: null
    }
  },
  methods: {
    fecharDialog() {
      this.$emit('close')
    },
    calcular() {
      const forca = this.forca
      const tensaoNormal = this.tensaoNormal
      const diametroParafuso = Math.sqrt((4 / Math.PI) * (forca / tensaoNormal))
      const diametroMM = (diametroParafuso * 1000).toFixed(2)
      this.diametroParafuso = diametroMM
    },
    limparCampos() {
      this.forca = null
      this.tensaoNormal = null
      this.diametroParafuso = null
    }
  }
}
</script>

<style lang="scss"></style>
