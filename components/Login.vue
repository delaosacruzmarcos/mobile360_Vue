<template>
  <View class="container">
    <view>
      <text>Email Address</text>
    </view>
    <text-input class="textField" v-model="username" />
    <view>
      <text>Password</text>
    </view>
    <text-input class="textField" v-model="password" />
    <!-- when the sign in button is clicked, check the database whether the user account exist or not, password correct or not, or the empty input field
    provide userful feedback to the user if sign in was not successful -->
    <button
      :on-press="signIn"
      title="Sign in"
      color="green"
      accessibility-label="Click here to Sign In"
    />
    <view>
      <text>Don't have an account yet?</text>
    </view>
    <button
      :on-press="register"
      title="Register here"
      color="green"
      accessibility-label="Click here to Register"
    />
  </View>
</template>

<script>
export default {
  data: function () {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    signIn: function () {
      this.$emit("changepage");
    },
    register: function () {
      this.$emit("register");
    },
  },
};
</script>

<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
}
.textField {
  height: 40;
  width: 300;
  border-color: gray;
  border-width: 1;
}
</style>