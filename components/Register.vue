<template>
  <form @submit="goLogin" class="container-fluid">
    <view class="row">
      <view class="col">
        <label for="fName">First Name</label>
        <input
          id="fName"
          type="text"
          class="form-control"
          placeholder="First name"
        />
      </view>
      <view class="col">
        <label for="lName">Last Name</label>
        <input
          id="lName"
          type="text"
          class="form-control"
          placeholder="Last name"
        />
      </view>
    </view>
    <view class="form-group">
      <label for="exampleInputEmail1">Email address</label>
      <input
        type="email"
        class="form-control"
        id="exampleInputEmail1"
        placeholder="Email"
      />
    </view>
    <view class="row">
      <view class="col">
        <label for="password">Password</label>
        <input
          id="password"
          type="password"
          class="form-control"
          placeholder="Password"
        />
      </view>
      <view class="col">
        <label for="confirmPassword">Confirm Password</label>
        <input
          id=""
          type="password"
          class="form-control"
          placeholder="Re-enter Password"
        />
      </view>
    </view>
    <view class="form-group">
      <label for="dob">Date of Birth</label>
      <input
        class="form-control"
        type="date"
        name="dob"
        id="dob"
        placeholder="Date of Birth"
      />
    </view>
    <button type="submit" class="btn btn-warning">Register</button>
    <p>
      <small> Already have an account? </small>
      <small style="color: green" @click="signin"> Sign in </small>
    </p>
  </form>
</template>

<script>
export default {
  name: "Register",
  methods: {
    signin() {
      this.$emit("signin");
    },
  },
};
</script>

<style scoped>
small {
  cursor: pointer;
}
</style>