<template>
  <div>
    <h1>Busquedas</h1>
    <input 
      type="text" 
      placeholder="Codigo del juego" 
      :value="$store.state.busquedaPorCodigo" 
      @input="$store.commit('SET_BUSQUEDA', $event.target.value)"
    />
    <ul>
        <li 
          v-for="juego in $store.getters.productoFiltrados" 
          :key="juego.codigo" 
          :style="{ backgroundColor: juego.color }"
          > 
          {{ juego.codigo }} | {{juego.nombre}} | {{juego.precio}} | {{juego.stock}} 
          </li>
    </ul>
    <Listado />
  </div>
</template>

<script>
import Listado from "@/components/Listado.vue";
export default {
  name: "BusquedasPage",
  components: {
    Listado,
  },
};
</script>

<style></style>