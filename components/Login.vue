<template>
  <div class="login">
    <h1 class="text-center">Login</h1>
    <b-form @submit="handleSubmit">
      <b-form-group label="Email address:" label-for="email">
        <b-form-input
          id="email"
          type="email"
          placeholder="Enter email"
          required
          v-model="email"
        ></b-form-input>
      </b-form-group>

      <b-form-group label="Password:" label-for="password">
        <b-form-input
          id="password"
          type="password"
          placeholder="Enter password"
          required
          v-model="password"
        ></b-form-input>
      </b-form-group>

      <b-button type="submit" variant="primary">Login</b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  name: "Login",
  props: ["title"],
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault();
      this.$router.push("/todo");
    },
  },
  mounted() {
    console.log("hello");
  },
};
</script>
<style>
.login {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 5px 10px;
  max-width: 624px;
  margin: 0 auto;
  padding: 46px 12px;
}
</style>
