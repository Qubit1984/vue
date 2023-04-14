<template>
  <div>
    <div>
      <pre>{{ JSON.stringify(formValues, null, 2) }}</pre>
    </div>
    <form @submit="submitForm">
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name" />

      <h2>{{ name }}</h2>
      <button v-on:click="changeName($event), increment(1, $event)">
        Change name
      </button>
      <button v-on:mouseover="name = 'ooo'">Change name</button>
      <div>
        <label for="profile">Profile Summary></label>
        <textarea id="profile" v-model="formValues.profileSummer"></textarea>
      </div>
      <h2>{{ 2 + 3 + 5 }}</h2>
      <h2>{{ count }}</h2>
      <h2>Add method-{{ add(2, 3, 10) }}</h2>
      <h2>Multipl method-{{ mutiply(baseValue) }}</h2>
      <div>
        <button v-on:click="increment(1, $event)">Increment</button>
        <button v-on:click="increment(5)">Increment5</button>
        <button @click="count -= 1">Decrement</button>
      </div>
      <div>
        <label for="job-location">Job Location</label>
        <select id="job-location" multiple v-model="formValues.joblocation">
          <option value="india">India</option>
          <option value="vietnam">Vietnam</option>
          <option value="singapore">Singapore</option>
        </select>
      </div>
      <div>
        <label for="country">Country</label>
        <select id="country" v-model="formValues.country">
          <option value="">Select a country</option>
          <option value="india">India</option>
          <option value="vietnam">Vietnam</option>
          <option value="singapore">Singapore</option>
        </select>
      </div>
      <div>
        <input
          type="checkbox"
          id="remotework"
          v-model="formValues.remotework"
          true-value="yes"
          false-value="no"
        />
        <label for="remotework">Open to remote work?</label>
      </div>
      <div>
        <label>Years of Experience</label>
        <input
          type="checkbox"
          id="html"
          value="html"
          v-model="formValues.yearsOfExperience"
        />
        <label for="html">0-2</label>
        <input
          type="checkbox"
          id="css"
          value="css"
          v-model="formValues.yearsOfExperience"
        />
        <label for="css">3-5</label>
        <input
          type="checkbox"
          id="javascript"
          value="javascript"
          v-model="formValues.yearsOfExperience"
        />
        <label for="javascript">JAVASCRIPT</label>
      </div>
      <div>
        <label>Skill set</label>
        <input
          type="radio"
          id="0-2"
          value="0-2"
          v-model="formValues.yearsOfExperience"
        />
        <label for="html">0-2</label>
        <input
          type="radio"
          id="3-5"
          value="3-5"
          v-model="formValues.skillSet"
        />
        <label for="css">CSS</label>
        <input
          type="radio"
          id="6-10"
          value="6-10"
          v-model="formValues.skillSet"
        />
        <label for="javascript">JAVASCRIPT</label>
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      formValues: {
        name: '',
        profileSummer: '',
        country: '',
        jobLocation: [],
        remotework: 'no',
        skillSet: [],
        yearsOfExperience: '',
      },
      name: 'Vishwas',
      baseMultiplier: 5,
      baseValue: 2,
      count: 0,
    };
  },
  methods: {
    submitForm(event) {
      event.preventDefault();
      console.log('Form values', this.formValues);
    },
    changeName(event) {
      (this.name = 'Batman'), console.log('Event', event);
    },
    add(a, b, c) {
      return a + b + c;
    },
    mutiply(num) {
      return num * this.baseMultiplier;
    },
    increment(num, event) {
      this.count += num;
      console.log('Event', event);
    },
    decrement(num) {
      this.count -= num;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
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
