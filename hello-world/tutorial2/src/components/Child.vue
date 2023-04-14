<template>
  <div>Child component</div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Child',
  beforeCreate() {
    console.log('Child beforeCreate()');
  },
  created() {
    console.log('Child created()');
  },
  beforeMount() {
    console.log('Child beforeMount()');
  },
  mounted() {
    console.log('Child mounted()');
  },
  beforeUpdate() {
    console.log('Child beforeUpdate()');
  },
  updated() {
    console.log('Child updated()');
  },
  beforeUnmount() {
    console.log('Child beforeUnmount()');
  },
  unmounted() {
    console.log('Child unmounted()');
  },
};
</script>

<style scoped>
</style>