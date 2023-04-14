<template>
  <div>
    <input type="text" placeholder="First Name" v-model="fName" />
    <input type="text" placeholder="Last Name" v-model="lName" />
    <input type="text" placeholder="Hero Name" v-model="heroName" />
    <input type="text" placeholder="First Name" v-model="fiestName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />
  </div>
</template>

<script>
import { ref, reactive, toRefs } from 'vue';
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Vmodel',
  setup() {
    const heroName = ref('');
    const state = reactive({
      firstName: '',
      lastName: '',
    });
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