<template>
  <div class="my-app">

    <div v-if="loggedIn">Witaj {{email}}
      <button @click="logMeOut()">Wyloguj</button>
    </div>

    <div v-else>
    <h1>Witaj w systemie do zapisow na zajecia</h1>
    <div>Zaloguj sie mailem:
    <input type="email" v-model="email">
      <button @click="logMeIn()">Wchodze</button></div>
    </div>


  </div>

</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
      loggedIn: false
    };
  },
  methods: {
    logMeIn() {
        this.loggedIn = true;
    },
    logMeOut() {
      this.loggedIn = false;
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
