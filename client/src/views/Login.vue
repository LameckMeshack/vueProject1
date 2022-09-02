<template>
  <div id="login-form-wrap">
    <h2>Login</h2>
    <form id="login-form" @submit.prevent="login">
      <p>
        <input
          type="text"
          id="username"
          name="username"
          placeholder="Username"
          required
        /><i class="validation"><span></span><span></span></i>
      </p>
      <p>
        <input
          type="password"
          id="password"
          name="password"
          placeholder="password "
          required
        /><i class="validation"><span></span><span></span></i>
      </p>
      <p>
        <input type="submit" id="login" value="Login" />
      </p>
    </form>
    <div id="create-account-wrap">
      <p>Not a member? <a href="#">Create Account</a></p>
      <p></p>
    </div>

    <!--create-account-wrap-->
  </div>
</template>
<script>
import { mapMutations } from "vuex";
export default {
  name: "LoginForm",
  data: () => {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    ...mapMutations(["setUser", "setToken"]),
    async login(e) {
      e.preventDefault();
      const response = await fetch("http://localhost:3000/login", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({
          username: this.username,
          password: this.password,
        }),
      });
      const { user, token } = await response.json();
      this.setUser(user);
      this.setToken(token);
      console.log(user);
    },
  },
};
</script>
<style lang="scss">
@import "../assets/css/styles.scss";
</style>

<!-- const response = await fetch("localhost:4000/users/authenticate", { -->
