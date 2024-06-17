<template>
    <table>
    <thead>
    <tr>
    <th>Artículo</th>
    <th>Precio</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="articulo in articulos" :key="articulo.nombre">
    <td>{{ articulo.nombre }}</td>
    <td>{{ articulo.precio }}</td>
    </tr>
    </tbody>
    </table>
    <p>Total: {{ total }}</p>
   </template>
   <script>
   import { computed } from 'vue';
   export default {
    props: {
    articulos: {
    type: Array,
    required: true,
    },
    },
    setup(props) {
    const total = computed(() =>
    props.articulos.reduce((sum, articulo) => sum + articulo.precio, 0)
    );
    return { total };
    },
   };
   </script>
   