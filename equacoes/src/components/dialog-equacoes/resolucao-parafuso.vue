<template>
  <v-row class="text-center">
    <v-col md="12" sm="12">
      <span class="text-h6">Desmembrando a equação:</span>
      <p>σ_adm = P / A</p>
      <p>Sendo: σ_adm => Tensão admissível, P => Força e A => Área</p>
      <p>Então teremos: <span class="font-weight-black">A = P / σ_adm</span></p>

      <p class="pt-3">Mas como o parafuso tem área circular:</p>
      <p class="font-weight-black">(π / 4) * d^2 = P / σ_adm</p>
      <p>Reformulando: d^2 = (4 / π) * P / σ_adm</p>

      <p class="font-weight-black">Sendo assim: d = √4 / π × ( P / σ_adm )</p>
      <p><span class="font-weight-black">"d"</span> é o diâmetro do parafuso</p>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'ResolucaoParafuso'
}
</script>
