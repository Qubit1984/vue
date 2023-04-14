<template>
  <div>
    <input type="text" placeholder="First Name" v-model="fName" />
    <input type="text" placeholder="Last Name" v-model="lName" />
    <input type="text" placeholder="First Name" v-model="refFirstName" />
    <input type="text" placeholder="Last Name" v-model="refLastName" />
    <h2>Options Fullname is {{ refFullName }}</h2>
    <input type="text" placeholder="First Name" v-model="reactiveFirstName" />
    <input type="text" placeholder="Last Name" v-model="reactiveLastName" />
    <h2>Reactive Fullname is {{ reactiveFullName }}</h2>
  </div>
</template>

<script>
import { ref, computed, reactive, toRefs } from 'vue';

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Computed',
  setup() {
    const refFirstName = ref('');
    const refLastName = ref('');
    const refFullName = computed(function () {
      return `${refFirstName.value} ${refLastName.value}`;
    });
    const state = reactive({
      reactiveFirstName: '',
      reactiveLastName: '',
    });
    const reactiveFullName = computed(function () {
      return `${state.reactiveFirstName} ${state.reactiveLastName}`;
    });
    return {
      refFirstName,
      refLastName,
      refFullName,
      reactiveFullName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      fName: '',
      lName: '',
    };
  },
};
</script>

<style scoped>
</style>