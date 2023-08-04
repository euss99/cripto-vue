<script setup>
import useCripto from "../composables/useCripto";
const { monedas, criptomonedas } = useCripto();

defineProps({
  moneda: {
    type: String,
    required: true,
  },
  criptomoneda: {
    type: String,
    required: true,
  },
});

defineEmits(["update:criptomoneda", "update:moneda", "cotizar-cripto"]);
</script>

<template>
  <form class="formulario" @submit.prevent="$emit('cotizar-cripto')">
    <div class="campo">
      <label for="moneda">Moneda:</label>
      <select
        id="moneda"
        :value="moneda"
        @input="$emit('update:moneda', $event.target.value)"
      >
        <option value="">--Selecciona--</option>
        <option v-for="moneda in monedas" :value="moneda.codigo">
          {{ moneda.texto }}
        </option>
      </select>
    </div>

    <div class="campo">
      <label for="cripto">Criptomoneda:</label>
      <select
        id="cripto"
        :value="criptomoneda"
        @input="$emit('update:criptomoneda', $event.target.value)"
      >
        <option value="">--Selecciona--</option>
        <option
          v-for="criptomoneda in criptomonedas"
          :value="criptomoneda.CoinInfo.Name"
        >
          {{ criptomoneda.CoinInfo.FullName }}
        </option>
      </select>
    </div>

    <input type="submit" value="Cotizar" />
  </form>
</template>
