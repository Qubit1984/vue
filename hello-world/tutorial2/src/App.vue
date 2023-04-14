<template>
  <div>
    <ClickCounter />
    <HoverCounter />
    <TemplateRef />
    <CreatePost />
    <PostList />
    <Parent />
  </div>
</template>

<script>
import PostList from './components/Postlist.vue';
import CreatePost from './components/CreatePost.vue';
import Parent from './components/Parent.vue';
import TemplateRef from './components/TemplateRef.vue';
import ClickCounter from './components/ClickCounter.vue';
import HoverCounter from './components/HoverCounter.vue';
export default {
  name: 'App',
  components: {
    PostList,
    CreatePost,
    Parent,
    TemplateRef,
    ClickCounter,
    HoverCounter,
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
