<template>
  <div class="grid grid-cols-1 sm:grid-cols-12 gap-4">
    <div class="sm:col-span-5 md:col-span-4">
      <InvestmentInput />
    </div>
    <div class="sm:col-span-7 md:col-span-8">
      <InvestmentSimulation />
    </div>
  </div>
</template>
<script setup lang="ts">
import { onMounted } from 'vue'
import { useInvestmentStore } from '~/store/investment'

useSeoMeta({
  title: 'Calculadora',
  description: 'Calculadora de investimentos Renda Fixa para simulação de rentabilidade em CDB, RDB, LC, LCI, LCA, Poupança e Tesouro Direto'
})

const store = useInvestmentStore()

// Inicializa índices no cliente para evitar possíveis efeitos colaterais no SSR
onMounted(() => {
  store.initializeStore()
})

</script>
