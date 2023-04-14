<template>
  <div>
    <h2>{{ firstName }} {{ lastName }}</h2>
  </div>
</template>
<script>
import { reactive, toRefs } from 'vue';
export default {
  name: 'DemeTwo',
  setup() {
    const state = reactive({
      firstName: 'Bruce',
      lastName: 'Wayne',
    });
    setTimeout(() => {
      (state.firstName = 'shiro'), (state.lastName = 'isana');
    }, 2000);
    return toRefs(state);
  },
};
</script>

<style scoped>
</style>