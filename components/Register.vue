<template>
  <View class="container">
    <view>
      <text>First Name</text>
    </view>
    <text-input class="textField" v-model="firstName" />
    <view>
      <text>Last Name</text>
    </view>
    <text-input class="textField" v-model="lastName" />
    <view>
      <text>Email Address</text>
    </view>
    <text-input class="textField" v-model="emailAddress" />
    <view>
      <text>Password</text>
    </view>
    <text-input class="textField" v-model="password" />
    <view>
      <text>Confirm Password</text>
    </view>
    <text-input class="textField" v-model="confirmPassword" />
    <view>
      <text>Date Of Birth</text>
    </view>
    <text-input class="textField" v-model="dateOfBirth" />
    <button
      :on-press="register"
      title="Register"
      color="green"
      accessibility-label="Click here to Register"
    />
    <view>
      <text>Already have an account?</text>
    </view>
    <button
      :on-press="signin"
      title="Sign In"
      color="green"
      accessibility-label="Click here to go to log in page"
    />
  </View>
</template>

<script>
export default {
  data: function () {
    return {
      firstName: "",
      lastName: "",
      emailAddress: "",
      password: "",
      firstName: "",
      confirmPassword: "",
      dateOfBirth: "",
    };
  },
  methods: {
    register: function () {
      alert("Register pressed");
    },
    signin: function () {
      this.$emit("signin");
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