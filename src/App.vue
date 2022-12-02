<template>
  <div id="app">
    <div class="container my-3">
      <div class="row">
        <div class="d-flex flex-column">
          <!-- Productos Infusiones -->
          <div class="col-12 mx-auto col-md-10 col-lg-8 col-xl-6">
            <h3 class="text-center">{{ titulo.infusiones }}</h3>
            <table class="table" :class="clase.infusiones">
              <thead>
                <tr>
                  <th scope="col">Nombre</th>
                  <th scope="col">Marca</th>
                  <th scope="col">Precio</th>
                  <th scope="col">Stock</th>
                </tr>
              </thead>
              <tbody>
                <tabla-info
                  is="tabla-info"
                  v-for="(infusion, index) in infusiones"
                  :key="index"
                  :nombre="infusion.nombre"
                  :marca="infusion.marca"
                  :precio="infusion.precio"
                  :stock="infusion.stock"
                  :class="infusion.stock ? '' : clase.sinstock"
                ></tabla-info>
              </tbody>
            </table>
          </div>

          <!-- Productos Chocolates -->
          <div class="col-12 mx-auto col-md-10 col-lg-8 col-xl-6">
            <h3 class="text-center">{{ titulo.chocolates }}</h3>
            <table class="table" :class="clase.chocolates">
              <thead>
                <tr>
                  <th scope="col">Nombre</th>
                  <th scope="col">Marca</th>
                  <th scope="col">Precio</th>
                  <th scope="col">Stock</th>
                </tr>
              </thead>
              <tbody>
                <tabla-info
                  is="tabla-info"
                  v-for="(chocolate, index) in chocolates"
                  :key="index"
                  :nombre="chocolate.nombre"
                  :marca="chocolate.marca"
                  :precio="chocolate.precio"
                  :stock="chocolate.stock"
                  :class="chocolate.stock ? 'haystock' : clase.sinstock"
                ></tabla-info>
              </tbody>
            </table>
          </div>

          <!-- Productos Leches -->
          <div class="col-12 mx-auto col-md-10 col-lg-8 col-xl-6">
            <h3 class="text-center" :class="clase.danger">{{ titulo.leches }}</h3>
            <table class="table" :class="clase.leches">
              <thead>
                <tr>
                  <th scope="col">Nombre</th>
                  <th scope="col">Marca</th>
                  <th scope="col">Precio</th>
                  <th scope="col">Stock</th>
                </tr>
              </thead>
              <tbody>
                <tabla-info
                  is="tabla-info"
                  v-for="(leche, index) in leches"
                  :key="index"
                  :nombre="leche.nombre"
                  :marca="leche.marca"
                  :precio="leche.precio"
                  :stock="leche.stock"
                  :class="leche.stock ? 'haystock' : clase.sinstock"
                ></tabla-info>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TablaInfo from "./components/TablaInfo.vue";

export default {
  name: "App",
  components: {
    TablaInfo,
  },
  data() {
    return {
      titulo: {
        infusiones: "Tabla Infusiones",
        chocolates: "Tabla Chocolates",
        leches: "Tabla Leches",
      },
      clase: {
        infusiones: ["text-center", "table-bordered"],
        chocolates: [
          "text-center",
          "table-dark",
          "table-hover",
          "table-bordered",
        ],
        leches: [
          "text-center",
          "table-bordered",
          "border-danger",
          "text-danger",
        ],
        sinstock: "sinStock",
        danger: "text-danger"
      },
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
