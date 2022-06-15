<template>
  <v-row class="text-center">
    <v-col md="12" sm="12">
      <span class="text-h6">Desmembrando a equação:</span>
      <p>A_suporte = P / τ_adm</p>
      <p>A_suporte também pode ser escrita como:</p>
      <p>A_suporte = π * (d_arruela) * h</p>
      <p class="font-weight-black">
        Sendo assim na formúla: h = 1/(π × d_arruela) × ( P/ τ_adm )
      </p>
      <p><span class="font-weight-black">"h"</span> é a espessura do teto</p>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'ResolucaoEspessuraTeto'
}
</script>
