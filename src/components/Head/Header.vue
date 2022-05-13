<template>
  <header>
    <nav class="navbar navbar-expand navbar-dark fixed-top bg-dark">
      <div class="container-fluid">
        <div class="collapse navbar-collapse" id="navbarCollapse">
          <ul class="navbar-nav me-auto mb-2 mb-md-0 mobile-ul">
            <li></li>
          </ul>
          <div class="d-flex">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Buscar..."
              aria-label="Search"
              v-model="dataBusqueda"
              @keyup="busqueda"
            />

            <button
              class="btn btn-outline-success w-50 cart"
              type="submit"
              @click.prevent="verCarrito"
            >
              <b-iconstack class="cart-color" font-scale="1">
                <b-icon stacked icon="cart-plus" variant="info"></b-icon>
              </b-iconstack>
              +<span class="pluscart">{{ totalValorYCantidad.totalCantidad }}</span>
            </button>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
export default {
  data() {
    return {
      dataBusqueda: "",
    };
  },
  computed: {
    ...mapGetters("Carrito", {
      totalValorYCantidad: "totalValorYCantidadProductos",
    }),
  },
  methods: {
    ...mapActions("Carrito", {
      verCarrito: "mostrarCarritoAction",
    }),
    busqueda() {
      // console.log(this.dataBusqueda);
      this.$router.push({
        name: "Busqueda",
        params: { name: this.dataBusqueda },
      });

      if (this.dataBusqueda == "") {
        this.$router.push({
          name: "Home",
        });
      }
    },
  },
};
</script>

<style lang="css" scoped>
.navbar-dark {
  background-color: #7e60a2 !important;
}
.cart{
  background-color:#fff
}
.pluscart{
  background-color:#6db87f;
  width:25px;
  height:25px;
  display:inline-block;
  color:#fff;
  border-radius:50%
}
.cart-color svg{
 fill:#000 !important
}

</style>
