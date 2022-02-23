<template>
  <header class="p-3">
    <img class="logo" src="../assets/logo.png" alt="">
  </header>
</template>

<script>
export default {
  name: 'MyHeader',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  header {
    background-color: #2e3a46;
    height: 80px;

    .logo {
      height: 100%;
    }
  }
</style>
