<template>
  <div id="app">
    <div class="container my-3">
      <div class="row">
        <div class="d-flex flex-column">
          <!-- Productos Infusiones -->
          <div class="col-12 mx-auto col-md-10 col-lg-8 col-xl-6">
            <table-component
              :array="infusiones"
              :title="tituloInfusiones"
              :clase="classInfusiones"
            >
            </table-component>
          </div>

          <!-- Productos Chocolates -->
          <div class="col-12 mx-auto col-md-10 col-lg-8 col-xl-6">
            <table-component
              :array="chocolates"
              :title="tituloChocolates"
              :clase="classChocolates"
            >
            </table-component>
          </div>

          <!-- Productos Leches -->
          <div class="col-12 mx-auto col-md-10 col-lg-8 col-xl-6">
            <table-component
              :array="leches"
              :title="tituloLeches"
              :clase="classLeches"
              :titleClass="danger"
            >
            </table-component>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TableComponent from "./components/TableComponent.vue";

export default {
  name: "App",
  components: {
    TableComponent,
  },
  data() {
    return {
      //Titulos
      tituloInfusiones: "Tabla Infusiones",
      tituloChocolates: "Tabla Chocolates",
      tituloLeches: "Tabla Leches",
      //Estilos
      classInfusiones: ["text-center", "table-bordered"],
      classChocolates: ["text-center", "table-dark", "table-hover", "table-bordered"],
      classLeches: ["text-center", "table-bordered", "border-danger", "text-danger"],
      sinstock: "sinStock",
      danger: "text-danger",
      //Productos
      infusiones: [
        {
          nombre: "Inti Grey",
          marca: "Inti Zen",
          precio: 354.12,
          stock: true,
        },
        {
          nombre: "Silencio Andino",
          marca: "Inti Zen",
          precio: 354.12,
          stock: true,
        },
        {
          nombre: "Patagonia Bee",
          marca: "Inti Zen",
          precio: 384.33,
          stock: false,
        },
      ],
      chocolates: [
        {
          nombre: "Chocolate 55% Cacao",
          marca: "Chocolate Colonial",
          precio: 341.45,
          stock: true,
        },
        {
          nombre: "Chocolate 70% Cacao + Stevia",
          marca: "Chocolate Colonial",
          precio: 389.35,
          stock: true,
        },
        {
          nombre: "Chocolate Para Taza",
          marca: "Chocolate Colonial",
          precio: 320.15,
          stock: true,
        },
      ],
      leches: [
        {
          nombre: "Leche de Almendras s/Azucar",
          marca: "Cocoon",
          precio: 410.56,
          stock: false,
        },
        {
          nombre: "Leche de Almendras Chocolatada",
          marca: "Cocoon",
          precio: 401.12,
          stock: true,
        },
        {
          nombre: "Leche de Almendras Original",
          marca: "Cocoon",
          precio: 401.12,
          stock: true,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
