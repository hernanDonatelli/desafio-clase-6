<template>
  <div>
    <h3 class="text-center" :class="titleClass">{{ title }}</h3>
    <table class="table" :class="clase">
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
          v-for="(producto, index) in array"
          :key="index"
          :nombre="producto.nombre"
          :marca="producto.marca"
          :precio="producto.precio"
          :stock="producto.stock"
          :class="producto.stock ? '' : dynclass.sinstock"
        ></tabla-info>
      </tbody>
    </table>
  </div>
</template>

<script>
import TablaInfo from "./TablaInfo.vue";

export default {
  name: "TableComponent",

  components: {
    TablaInfo,
  },

  props: ["title", "clase", "titleClass", "array"],

  data() {
    return {
      dynclass: {
        sinstock: "sinStock",
      },
    };
  },
};
</script>
