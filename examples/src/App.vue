<template>
  <div id="app" class="container">
    <ul class="nav nav-tabs">
      <li v-bind:class="{ active: currentTab === 'SignUp' }"><a href="#" @click="switchTab('SignUp')">Sign Up</a></li>
      <li v-bind:class="{ active: currentTab === 'Login' }"><a href="#" @click="switchTab('Login')">Login</a></li>
      <li><a href="#" @click="switchTab('UserConfirmation')">User Confirmation</a></li>
      <li><a href="#" @click="switchTab('PasswordConfirmation')">Password Confirmation</a></li>
    </ul>
    <SignUp v-if="currentTab === 'SignUp'"></SignUp>
    <Login v-if="currentTab === 'Login'"></Login>
    <UserConfirmation v-if="currentTab === 'UserConfirmation'"></UserConfirmation>
    <PasswordConfirmation v-if="currentTab === 'PasswordConfirmation'"></PasswordConfirmation>
  </div>
</template>

<script>
import Login from './components/Login';
import SignUp from './components/SignUp';
import UserConfirmation from './components/UserConfirmation';
import PasswordConfirmation from './components/PasswordConfirmation';

export default {
  name: 'app',
  components: {
    Login,
    SignUp,
    UserConfirmation,
    PasswordConfirmation,
  },
  data: () => ({
    currentTab: 'SignUp',
  }),
  methods: {
    switchTab(tab) {
      this.currentTab = tab;
    },
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.nav-tabs {
  margin-bottom: 25px;
}
</style>
