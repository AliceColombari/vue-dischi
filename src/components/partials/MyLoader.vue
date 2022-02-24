<template>
  <!-- aggiunto loading in caso di caricamente lento della pagina / connessione lenta -->
  <div class="loader">
      Loading...
  </div>
</template>

<script>
export default {
    name: "MyLoader",
}
</script>

<style scoped lang="scss">
  .loader {
    font-size: 30px;
    color: #fff;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
</style>