<template>
  <div>
    <h2>Component F</h2>
    <h3>Componenet F username {{ username }}</h3>
  </div>
</template>

<script>
export default {
  name: 'ComponentF',
  inject: ['username'],
};
</script>

<style scoped>
</style>