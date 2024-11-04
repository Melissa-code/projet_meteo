<template>
  <div id="app">
    <meteoComponent></meteoComponent>
  </div>
</template>

<script>
  import MeteoComponent from './components/MeteoComponent.vue'

  export default {
    name: 'App',
    components: {
      'meteoComponent': MeteoComponent,
    }
  }
</script>

<style>
  body {
    background: #ffd89b;  /* cf. UI gradients.com fallback for old browsers */
    background: -webkit-linear-gradient(to right, #19547b, #ffd89b);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #19547b, #ffd89b); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  }

</style>
