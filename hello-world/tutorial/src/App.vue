<template>
  <div>
    <teleport to="#portal-root">
      <Portal />
    </teleport>
    <button @click="activeTab = 'TabA'">Tab A</button>
    <button @click="activeTab = 'TabB'">Tab B</button>
    <button @click="activeTab = 'TabC'">Tab C</button>
    <keep-alive>
      <component :is="activeTab" />
    </keep-alive>
    <!--<TabA v-if="activeTab === 'TabA'" />
    <TabB v-if="activeTab === 'TabB'" />
    <TabC v-if="activeTab === 'TabC'" />-->
    <h4>APP COMPONENT TEXT</h4>
    <ChildStyles>
      <h4>childstyle</h4>
    </ChildStyles>
    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }}{{ slotProps.lastName }}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }},{{ slotProps.lastName }}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps"> {{ slotProps.firstName }}</template>
    </NameList>
    <Card>Card</Card>
    <Card>
      <h2>ssss</h2>
    </Card>
    <Card>
      <img src="http://picsum.photos/200" />
    </Card>
    <Card content="Card conten 2" />
    <Card />
    <Input v-model="name" />
    <button @click="showPopup = true">Show Popup</button>
    <Popup v-show="showPopup" @close="closePopup" />
    <h3>AppComponent username{{ name }}</h3>
    <ComponentC />
    <Greet name="Bruce" heroName="Batman" />
    <Greet name="Clark" heroName="Superman" />
    <Greet name="Diana" heroName="Wonder Woman" />
    <Article
      id="my-article"
      title="Article Title"
      :likes="50"
      :isPublished="true"
    />
  </div>
</template>

<script>
import Greet from './components/Greet.vue';
import Article from './components/Article.vue';
import ComponentC from './components/ComponentC.vue';
import Popup from './components/Popup.vue';
import Input from './components/input.vue';
import Card from './components/card.vue';
import NameList from './components/NameList.vue';
import ChildStyles from './components/ChildStyle.vue';
import TabA from './components/TabA.vue';
import TabB from './components/TabB.vue';
import TabC from './components/TabC.vue';
import Portal from './components/Portal.vue';
export default {
  name: 'App',
  components: {
    Greet,
    Article,
    ComponentC,
    Popup,
    Input,
    Card,
    NameList,
    ChildStyles,
    TabA,
    TabB,
    TabC,
    Portal,
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
  display: block;
  justify-content: center;
}
h4 {
  color: orange;
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
