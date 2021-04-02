<template>
  <view class="container">
    <view class="nav-bar">
      <Header @drawer="openDrawer" :title="title"></Header>
    </view>
    <image-background
      :source="require('../assets/background.png')"
      class="background"
    >
      <image class="avatar" :source="require('../assets/ww.png')" />
    </image-background>
    <touchable-opacity class="content">
      <text class="notification-text"
        >welcome to the homepage (possible custom graphic)
      </text>
    </touchable-opacity>
    <scroll-view>
      <touchable-opacity class="content">
        <text class="notification-text">posting sections</text>
      </touchable-opacity>
      <touchable-opacity class="content">
        <text class="notification-text">posting section</text>
      </touchable-opacity>
    </scroll-view>
    <view class="bottomBar"></view>
  </view>
</template>

<script>
import Header from "../components/header";
import React from "react";
import {
  ImageBackground,
  View,
  StyleSheet,
  TouchableOpacity,
  Text,
} from "react-native";
import { Card } from "react-native-paper";
export default {
  props: {
    navigation: { type: Object },
  },
  data() {
    return {
      title: "Home",
    };
  },
  methods: {
    openDrawer: function() {
      this.navigation.openDrawer();
    },
  },
  components: { Header },
};
</script>

<style>
.nav-bar {
  background-color: green;
}
.container {
  flex: 1;
  /* padding-left: 20px;
  padding-right: 20px;
  align-items: center;
  background-color: #ffffff; */
}
.text-style {
  font-size: 20;
  color: yellow;
}
.content {
  border-bottom-width: 1;
  border-color: #d9d9d9;
  padding: 75;
  align-items: center;
}
.homePage-text {
  padding: 0;
  font-size: 30px;
  color: black;
  text-align: center;
}
.card-header-container {
  width: 100%;
  height: 43%;
  align-items: center;
  display: flex;
  flex-direction: row;
}
.background {
  align-items: center;
}
.avatar {
  height: 130px;
  width: 130px;
  border-radius: 100;
  background-color: rgba(245, 255, 226, 0.322);
  overflow: hidden;
}
</style>
