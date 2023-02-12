<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from './components/HelloWorld.vue';

export type Datatype ={
	site_setting: Object
	first_comment_bot_messages: Array<Object>
	messageInput: string | null
	isChange: boolean
}


type Profile =  {
  favoriteFood: string,
  hobby: string,
  specialSkills: string
}

type User = {
  name: string;
  age?: number;
  profile: Profile;
}

type Params = {
  "pass_site_setting": {
    "is_use_first_comment_bot": boolean
  }
}

export default Vue.extend({
  name: 'App',
  components: {
    HelloWorld,
  },
  data(): User {
    return {
      name: "ryotaro",
      // age: 26,
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
    async reqestProfile(profile: Profile): Promise<Profile | void> {
      return {
        favoriteFood: "いちご",
        hobby: "バドミントン",
        specialSkills: "プログラミング",
      };
    },
  },
});
</script>
