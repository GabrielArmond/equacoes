<template>
  <div class="conteudo">
    <Header />
    <CardEquacao @abrirDialog="abrirDialog" />

    <v-dialog
      persistent
      v-model="dialog_parafuso"
      transition="fade-transition"
      max-width="800"
    >
      <transition>
        <DialogParafuso
          v-if="dialog_parafuso"
          @close="dialog_parafuso = false"
          titulo="Equação para diâmetro do parafuso"
        />
      </transition>
    </v-dialog>

    <v-dialog
      persistent
      v-model="dialog_teto"
      transition="fade-transition"
      max-width="800"
    >
      <transition>
        <DialogTeto
          v-if="dialog_teto"
          @close="dialog_teto = false"
          titulo="Equação para espessura do teto"
        />
      </transition>
    </v-dialog>
  </div>
</template>

<script>
import DialogParafuso from '@/components/dialog-equacoes/dialog-parafuso.vue'
import DialogTeto from '@/components/dialog-equacoes/dialog-teto.vue'
import Header from '@/components/header-equacao.vue'
import CardEquacao from '@/components/card-equacao.vue'

export default {
  name: 'Home-equation',

  components: {
    Header,
    CardEquacao,
    DialogParafuso,
    DialogTeto
  },
  data() {
    return {
      dialog_parafuso: false,
      dialog_teto: false
    }
  },

  methods: {
    abrirDialog(equacao) {
      if (equacao.id === 0) {
        this.dialog_parafuso = true
      } else {
        this.dialog_teto = true
      }
    }
  }
}
</script>

<style lang="scss">
.conteudo {
  height: 100vh;
  border: 1px solid gray;
  border-radius: 20px;
}
</style>
