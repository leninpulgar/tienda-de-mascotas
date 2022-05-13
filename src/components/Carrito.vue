<template>

<!-- Recuadro del Carrito -->
  <div class="mt-5 carrito container pt-3" v-show="visible">
    <h3>Resumen de Compra</h3>

    <!-- Producto  -->
    <div
      class="row mb-2"
      v-for="producto in totalProductos"
      :key="producto.index"
    >
      <ProductosCarrito :producto="producto"></ProductosCarrito>
    </div>

    <hr />
    <div class="row d-flex justify-content-center">
      <div class="col-12m w-50 d-flex justify-content-between">
        <p>Total</p>
        <b>${{ totalValorYCantidad.totalValor }}</b>
      </div>
    </div>
  </div>
</template>
<!-- Recuadro del carrito END -->

<script>
import { mapGetters } from "vuex";
import ProductosCarrito from "./ProductosCarrito.vue";
export default {
  data() {
    return {};
  },
  components: {
    ProductosCarrito,
  },
  computed: {
    ...mapGetters("Carrito", {
      visible: "carritoStadoGet",
      totalProductos: "totalProductosGet",
      totalValorYCantidad: "totalValorYCantidadProductos",
    }),
  },
};
</script>

<style lang="css" scoped>
.carrito {
  position: fixed;
  left: 60%;
  top: 1%;
  z-index: 1;
  border: 1px solid #777;
  border-radius:10px;
  width: 40%;
  height: auto;
  background-color: white;
}
</style>
