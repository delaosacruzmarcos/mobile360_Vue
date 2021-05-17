<template>
  <view class="header-container">
    <touchable-opacity :on-press="openDrawer">
      <image class="icon" :source="require('../assets/icons8-menu-100.png')" />
    </touchable-opacity>
    <view class="title-container">
      <text class="header-title">{{ title }}</text>
    </view>
  </view>
</template>

<script>
import { Alert } from "react-native";
export default {
  props: {
    navigation: { type: Object },
    title: String,
  },
  data() {
    return {};
  },
  methods: {
    openDrawer: function() {
      this.$emit("drawer");
    },
  },
};
</script>

<style>
.header-container {
  width: 100%;
  padding-top: 5%;
  align-items: center;
  flex-direction: row;
  background-color: green;
}
.icon {
  width: 32px;
  height: 32px;
  margin: 5px;
}
.title-container{
    flex: 1;
    align-items: center;
    margin-right: 35px;
}
.header-title {
  font-size: 20px;
  font-weight: bold;
  color: #F1C40F;
}
</style>
