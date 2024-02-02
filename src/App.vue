<script setup>
  import Calculadora from './components/calculadora.vue'
</script>

<template>
  <div id="app">
    <div class="container">
      <Calculadora />
    </div>
  </div>
</template>

<script>
  export default {
    name: 'App',
    components: {
      Calculadora
    }
  }
</script>

<style>
  .container {
    max-width: 720px;
    height: 90svh;
    position: relative;
    margin: 0 auto;
  }
</style>