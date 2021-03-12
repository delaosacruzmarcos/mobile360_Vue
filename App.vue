<template>
<view class="container" v-if="!isLogin">
    <text class="text-color-primary">HELLO WORLD</text>
</view>
<view class="image-container" v-else-if="isLogin">
  <image
    :style="{width: 160, height: 100}"
    :source="require('./assets/dw.png')"
  />
  <text class="title">Younite360</text>
  <Login />
  <!-- <component @changepage="changePage" @signin="signin" @register="register" :is="which"></component> -->
</view>
</template>

<script>
import Login from "./components/Login";
import Register from "./components/Register";

export default {
  name: "App",
  components: {
    //appLogin: Login,
    //Register
    Login
  },
  data() {
    return {
      isLogin: true,
      //currently set to register
      //which: "app-register",
    };
  },
  methods: {
    changePage() {
      this.isLogin = !this.isLogin;
    },
    register() {
      this.which = "app-register";
    },
    signin() {
      this.which = "app-login";
    },
  },
};
</script>

<style>
.container {
  flex: 1;
  background-color: white;
  align-items: center;
  justify-content: center;
}
.image-container {
  flex: 1;
  align-items: center;
  justify-content: center;
  margin-top: 30%;
}
.title {
  color: black;
  font-size: 50;
}
.text-color-primary {
  color: blue;
  font-size: 30;
}

.common {
  background-color: whitesmoke;
}
.search {
  border-radius: 100px;
}
</style>