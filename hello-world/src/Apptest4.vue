<template>
  <div>
    <h2>Volume Tracker(0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>
    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />
    <div>
      <button @click="movielist.push('wonder woman')">add movie</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      volume: 0,
      movie: '',
      movieInfo: {
        title: '',
        actor: '',
      },
      movielist: ['Batman', 'Superman'],
    };
  },
  methods: {},
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
  display: block;
  justify-content: center;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 8px;
}
input-label {
  font-weight: bold;
  display: flex;
  margin-bottom: 20px;
}
input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px;
}
</style>
