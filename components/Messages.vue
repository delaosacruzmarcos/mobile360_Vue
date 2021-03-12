<template>
  <view class="container">
    <text class="text-color-primary">{{ message }}</text>
    <button title="Go to home screen" @press="goToHomeScreen"></button>
  </view>
</template>

<script>
export default {
  props: {
    navigation: { type: Object }
  },
  data() {
    return {
      message: "Messages Page"
    };
  },
  methods: {
      goToHomeScreen() {
      this.navigation.navigate("HomeScreen");
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
.text-color-primary {
  color: blue;
  font-size: 30;
}
</style>