<template>
  <AgregarArticulo @articuloAgregado="articulos.push($event)" />
  <ListaArticulos :articulos="articulos" />
 </template>
 <script>
 import { ref } from 'vue';
 import AgregarArticulo from './components/AgregarArticulo.vue';
 import ListaArticulos from './components/ListaArticulos.vue';
 export default {
  components: { AgregarArticulo, ListaArticulos },
  setup() {
  const articulos = ref([]);
  return { articulos };
  }
 };
 </script>