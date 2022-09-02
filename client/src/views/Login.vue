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
          v-model="username"
          required
        /><i class="validation"><span></span><span></span></i>
      </p>
      <p>
        <input
          type="password"
          id="password"
          name="password"
          placeholder="password "
          v-model="password"
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
<!-- <script>
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
</script> -->

<script>
import axios from "axios";
// import { mapActions } from "vuex";
export default {
  name: "LoginForm",
  data: () => {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    // ...mapActions(["setUser", "setToken"]),
    async login(e) {
      e.preventDefault();
      const response = await axios.post("http://localhost:3000/login", {
        username: this.username,
        password: this.password,
      });
      const { token, user } = response.data;
      // this.setUser(user);
      // this.setToken(token);
      // console.log(user);
      // console.log(token);
      // login action
      this.$store.dispatch("login", { token, user });

      this.$router.push({ name: "home" });
    },
  },
};
</script>

<style lang="scss">
@import "../assets/css/styles.scss";
</style>
