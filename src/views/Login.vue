<template>
  <div>
    <h2>登録</h2>
    <label for="email">Email：</label>
    <input
      id="email"
      type="email"
      v-model="email"
    >
    <br><br>
    <label for="password">パスワード：</label>
    <input
      id="password"
      type="password"
      v-model="password"
    >
    <br><br>
    <button @click="login">送信</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    login() { 
      axios.post(
        '/accounts:signInWithPassword?key=AIzaSyBQRS7-T5L40DlRasWCNqG6tQCq8F2cOZw',
        {
          email: this.email,
          password: this.password,
          returnSecureToken: true
        }
      )
    this.email = "";
    this.password = "";
    }
  }
};
</script>