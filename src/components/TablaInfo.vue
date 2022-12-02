<template>
    <tr>
      <td>{{nombre}}</td>
      <td>{{marca}}</td>
      <td>{{precio}}</td>
      <td>{{stock ? 'Hay stock' : 'Sin stock'}}</td>
    </tr>
</template>

<script>
export default {
  name: "TablaInfo",
  props: {
    nombre: String,
    marca: String,
    precio: Number,
    stock: Boolean
  },
};
</script>

<style scoped>
.sinStock{
    color: rgb(173, 173, 173);
}
</style>