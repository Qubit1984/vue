<!-- eslint-disable vue/multi-word-component-names -->
<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h2>Option -{{ o_firstname }}</h2>
    <h2>Composition-{{ c_firstName }}</h2>
    <h2>Composition- {{ greet }}</h2>

    <h2>Composition- {{ greetHero }}</h2>
    <h2>Composition- {{ reactiveGreetHero }}</h2>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Date',
  setup() {
    const c_firstName = ref('Clark');
    const c_lastName = ref('Kent');
    const c_heroName = ref('Superman');
    c_firstName.value = 'Diana';
    const greet = `Hello ${c_firstName.value}`;
    const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`;
    const state = reactive({
      firstName: 'shiro',
      lastName: 'isana',
      heroName: 'vvv',
    });
    const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`;
    return {
      c_firstName,
      greet,
      c_lastName,
      c_heroName,
      greetHero,
      reactiveGreetHero,
    };
  },
  data() {
    return {
      o_firstname: 'Bruce',
    };
  },
};
</script>

<style scoped>
</style>