<template>
  <base-container title="Vuex" v-if="isAuth">
    <the-counter></the-counter>
    <favorite-value></favorite-value>
    <button @click="addOne({value: 10})">Add 10</button>
    <change-counter></change-counter>
  </base-container>
  <base-container>
    <user-auth></user-auth>
  </base-container>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import TheCounter from './components/TheCounter';
import ChangeCounter from './components/ChangeCounter';
import FavoriteValue from './components/FavoriteValue';
// import { mapActions } from 'vuex'
import UserAuth from './components/UserAuth';

export default {
  components: {
    UserAuth,
    FavoriteValue,
    ChangeCounter,
    TheCounter,
    BaseContainer,
  },
  computed: {
    isAuth() {
      return this.$store.getters.userIsAuthenticated
    }
  },
  methods: {
    addOne() {
      this.$store.dispatch('numbers/increase', { value: 10 })
    }
    // ...mapActions(['numbers/increase'])
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>