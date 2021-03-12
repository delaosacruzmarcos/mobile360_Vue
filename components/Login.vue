<template>
  <View class="container">
    <view>
      <text>Email Address</text>
    </view>
    <text-input
      :style="{ height: 40, width: 300, borderColor: 'gray', borderWidth: 1 }"
      v-model="username"
    />
    <view>
      <text>Password</text>
    </view>
    <text-input
      :style="{ height: 40, width: 300, borderColor: 'gray', borderWidth: 1 }"
      v-model="password"
    />
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
      alert("Sign in pressed");
    },
    register: function () {
      alert("Register pressed, navigating to register page");
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
/* .text-container {
  flex: 1;
} */
</style>