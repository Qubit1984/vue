<template>
  <div>
    <h2>{{ name }}</h2>
    <button @click="setName">Change name</button>
    <h2>{{ count }}</h2>
    <button @click="incrementCount">Increment count</button>
    <h2>{{ first }} {{ last }}</h2>
    <button @click="changeHero">Change Hero</button>
  </div>
</template>

<script>
import { reactive, ref, toRefs } from 'vue';
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Methods',
  setup() {
    const count = ref(0);
    const state = reactive({
      first: 'Bruce',
      last: 'Wayne',
    });
    function incrementCount() {
      count.value++;
    }
    function changeHero() {
      state.first = 'Clark';
      state.last = 'Kent';
    }
    return { count, incrementCount, ...toRefs(state), changeHero };
  },
  data() {
    return {
      name: 'Vishwas',
    };
  },
};
</script>

<style scoped>
</style>