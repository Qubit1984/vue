<template>
  <div>
    <Computed />
    <Methods />
    <DemoTwo />
    <DemoOne />
    <Data />
  </div>
</template>

<script>
import Computed from './components/Computed.vue';
import Data from './components/Data.vue';
import DemoOne from './components/DemoOne.vue';
import DemoTwo from './components/DemoTwo.vue';
import Methods from './components/Methods.vue';

export default {
  name: 'App',
  components: {
    Data,
    DemoOne,
    DemoTwo,
    Methods,
    Computed,
  },

  data() {
    return {
      name: '',
      channel: 'yashiro',
      showPopup: false,
      activeTab: 'TabA',
    };
  },
  provide() {
    return { username: this.name };
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      console.log('name', name);
    },
  },
  computed: {},
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert('too high');
      }
    },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name=${newValue}`);
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(`Calling API with movie name=${newValue}`);
      },
      deep: true,
    },
    movielist: {
      handler(newValue) {
        console.log(`Calling API with movie name=${newValue}`);
      },
      deep: true,
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
