<template>
  <div class="my-app">

    <div v-if="authenticatedUserName.length > 0">Witaj {{authenticatedUserName}}
      <button @click="logMeOut()">Wyloguj</button>
    </div>

    <div v-else>
      <LoginForm @login="(username) => logMeIn(username)"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" button-label="Wejdź"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" button-label="Wleć"></LoginForm>
      <LoginForm @@login="(username) => logMeIn(username)" button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></LoginForm>
    </div>

  </div>

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
  components: {LoginForm},
  data() {
  return {
    authenticatedUserName: '',
    password: '',
  };
},
methods: {
  logMeIn(username) {
      this.authenticatedUserName = username;
  },
  logMeOut() {
    this.authenticatedUserName = '';
  }
}
}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
