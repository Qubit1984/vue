<template>
  <div>
    <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>
    <h2 v-for="name in fullNames" :key="name.first">
      {{ name.first }} {{ name.last }}
    </h2>
    <h2 v-for="(value, key, index) in myInfo" :key="value">
      {{ index }}{{ key }} {{ value }}
    </h2>
    <div>{{ greet }}{{ name }}</div>
    <div v-html="channel"></div>
    <h2 v-if="num === 0">The number is zero</h2>
    <h2 v-else-if="num < 0">The number is negative</h2>
    <h2 v-else-if="num > 0">The number is posotive</h2>
    <h2 v-else>Not a number</h2>
    <template v-if="display">
      <h2>Vishwas</h2>
      <h2>Codevolution</h2>
      <h2>Vue</h2></template
    >
    <h2 v-show="showElement">Using v-show</h2>
    <h2 v-bind:id="headingId">Heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>
    <h2 class="underline">Underline text</h2>
    <h2 class="underline" v-bind:class="status">Status</h2>
    <h2 v-bind:class="isPrompted && 'promoted'">Promoted Movie</h2>
    <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout?movie</h2>
    <h2 v-bind:class="['new', 'promoted']">Newly promoted movie</h2>
    <h2
      v-bind:class="[isPrompted && 'promoted', isSoldout ? 'sold-out' : 'new']"
    >
      Array conditional movie
    </h2>
    <h2
      v-bind:class="{
        promoted: isPrompted,
        new: !isSoldout,
        'sold-out': isSoldout,
      }"
    >
      Object conditional movie
    </h2>
    <h2
      v-bind:style="{
        color: highlightColor,
        fontSize: headerSize + 'px',
        padding: '20px',
      }"
    >
      Inline Style
    </h2>
    <h2 v-bind:style="headerStyleObject">Style Style</h2>
    <div v-bind:style="[baseStyleObject, successStyleObject]">
      Success Style
    </div>
    <div v-bind:style="[baseStyleObject, dangerStyleObject]">Danger Style</div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      names: ['Bruce', 'Clark', 'Diana'],
      fullNames: [
        { first: 'Bruce', last: 'Diana' },
        { first: 'Clark', last: 'Diana' },
        { first: 'Diana', last: 'Diana' },
      ],
      myInfo: { a: 'sss', b: 'sssss', c: 'qqqqq' },
      num: 5,
      display: true,
      showElement: true,
      greet: 'Hello',
      name: 'Vishwas',
      channel: '<b>Codevolution</b>',
      headingId: 'heading',
      isDisabled: false,
      status: 'danger',
      isPrompted: true,
      isSoldout: true,
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px',
      },
      baseStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
      },
      dangerStyleObject: {
        color: 'darked',
        backgroundColor: 'red',
        border: '1px solid darked',
      },
    };
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
.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}
.new {
  color: aqua;
}
.sold-out {
  color: red;
}
</style>
