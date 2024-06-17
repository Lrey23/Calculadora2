<template>
    <input v-model="nuevoArticulo.nombre" placeholder="Nombre de artículo">
    <input v-model="nuevoArticulo.precio" type="number" placeholder="Precio">
    <button @click="agregarArticulo">Agregar</button>
   </template>
   <script>
   import { ref } from 'vue';
   export default {
    emits: ['articuloAgregado'],
    setup(props, { emit }) {
    const nuevoArticulo = ref({ nombre: '', precio: 0 });
    const agregarArticulo = () => {
    emit('articuloAgregado', { ...nuevoArticulo.value });
    nuevoArticulo.value = { nombre: '', precio: 0 };
    };
    return { nuevoArticulo, agregarArticulo };
    }
   };
   </script>