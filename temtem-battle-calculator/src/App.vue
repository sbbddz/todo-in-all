<template>
  <MainCalculator/>
</template>

<script>
import MainCalculator from './components/MainCalculator'

export default {
  name: 'App',
  components: {
    MainCalculator,
  }
}
</script>

<style>
#app {
  display: flex;
  min-height: 100vh;
  min-width: 100vw;
  justify-content: center;
  align-items: center;
}

body {
  margin: 0px;
}
</style>
