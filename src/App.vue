<template>
  <div id="app">
    <router-view v-if="isLoggedIn"></router-view>
    <TheLogin v-else @TheLogin::loginResult="handleLoginResult" />
  </div>
</template>

<script>
import TheLogin from "./components/TheLogin";
export default {
  name: "app",
  components: {
    TheLogin
  },
  data() {
    return {
      userIsLoggedIn: false
    };
  },
  computed: {
    isLoggedIn() {
      return this.userIsLoggedIn;
    }
  },
  methods: {
    handleLoginResult({ loginResult }) {
      this.userIsLoggedIn = loginResult;
    }
  }
};
</script>