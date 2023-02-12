<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from './components/HelloWorld.vue';

type Profile =  {
  favoriteFood: string,
  hobby: string,
  specialSkills: string
}

type User = {
  name: string;
  age: number;
  profile: Profile;
}

export default Vue.extend({
  name: 'App',
  components: {
    HelloWorld,
  },
  data(): User {
    return {
      name: "ryotaro",
      age: 26,
      profile:{
        favoriteFood: "いちご",
        hobby: "バドミントン",
        specialSkills: "プログラミング"
      }
    }
  },
  computed: {
    isEnabled(): boolean {
      return true;
    },
    getCount(): number {
      return 1;
    },
  },
  methods: {
    async reqest() {
      return 1;
    },
  },
});
</script>
