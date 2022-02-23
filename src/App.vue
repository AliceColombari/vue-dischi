<template>
  <div id="app">
    <MyHeader/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
</style>
