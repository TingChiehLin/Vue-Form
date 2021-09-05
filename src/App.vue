<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Form @set-data="setUserDate"/>
    <VModel/>
  <Result>
    <div class="name">User Name: {{ user.name }}</div>
    <div class="name">User Referrer: {{ user.referrer }}</div>
    <ul class="list-of-array">
      <li v-for="(interest, index) in user.interest" :key="index">
        User Interest: {{ interest }}
      </li>
    </ul>
  </Result>
</template>

<script>
import Form from './components/Form.vue'
import VModel from "./components/VModel";
import Result from './components/Result';

export default {
  name: 'App',
  components: {
    Form,
    VModel,
    Result
  },
  data() {
    return {
      user: {
        name: "",
        referrer: "",
        interest: []
      }
    }
  },
  methods: {
    setUserDate(userName, referrer, interest) {
      this.user = {
        name: userName,
        referrer,
        interest
      }
    }
  }
}
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

.name {
  font-size: 24px;
}

.list-of-array {
  list-style: none;
  font-size: 24px;
}

</style>
