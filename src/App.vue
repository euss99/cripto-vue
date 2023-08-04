<script setup>
import { ref, reactive } from "vue";
import Alerta from "./components/Alerta.vue";
import Spinner from "./components/Spinner.vue";
import useCripto from "./composables/useCripto.js";
import Cotizacion from "./components/Cotizacion.vue";
import Formulario from "./components/Formulario.vue";

const { cotizacion, cargando, obtenerCotizacion, mostrasResultado } =
  useCripto();

const error = ref("");
const cotizar = reactive({
  moneda: "",
  criptomoneda: "",
});

const cotizarCripto = () => {
  if (Object.values(cotizar).includes("")) {
    error.value = "Todos los campos son obligatorios";

    setTimeout(() => {
      error.value = "";
    }, 3000);
    return;
  }

  error.value = "";
  obtenerCotizacion(cotizar);
};
</script>

<template>
  <div class="contenedor">
    <h1 class="titulo">Cotizador de <span>criptomonedas</span></h1>

    <div class="contenido">
      <Alerta v-if="error">{{ error }}</Alerta>

      <Formulario
        v-model:moneda="cotizar.moneda"
        v-model:criptomoneda="cotizar.criptomoneda"
        @cotizar-cripto="cotizarCripto"
      />

      <div v-if="cargando" class="loading">
        <Spinner />
      </div>

      <Cotizacion v-if="mostrasResultado" :cotizacion="cotizacion" />
    </div>
  </div>
</template>
