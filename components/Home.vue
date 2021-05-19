<template>
  <view class="container">
    <view class="nav-bar">
      <Header @drawer="openDrawer" :title="title"></Header>
    </view>
    <image-background

      :source="require('../assets/background.png')"
      class="background"
    >
      <image class="avatar" :source="require('../assets/k9UserAvatar.png')" />
    </image-background>
    <!-- <touchable-opacity class="content">
      <text class="notification-text"
        >User data displayed here
      </text>
    </touchable-opacity> -->
    <scroll-view>
         
    <touchable-opacity>
      <view class ="header-container">
        <image class="icon" :source="require('../assets/user.png')" />
        <view class="title-container">
          <text class="header-title">K9 user</text>
        </view>
      </view>
      <view class ="content">
        <image :source ="require('../assets/dogForPost.png')" />
      </view>
    </touchable-opacity>

  


      <touchable-opacity>
          <view class ="header-container">
        <image class="icon" :source="require('../assets/user.png')" />
        <view class="title-container">
          <text class="header-title">k9 user</text>
        </view>
      </view>
        <view class="container">
        <image :source ="require('../assets/dogForPost2.png')" />
        </view>
      </touchable-opacity>  
    </scroll-view>
    <view class="bottomBar"></view>
  </view>
</template>

<script>
import React from "react";
import {
  ImageBackground,
  View,
  StyleSheet,
  TouchableOpacity,
  Text,
} from "react-native";
import { Card } from "react-native-paper";
import Header from './header.vue';
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
  border-color:green;
  padding: 25;
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
.header-container {
  width: 100%;
  padding-top: 2%;
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
    align-items: center ;
    margin-right: 35px;
}
.header-title {
  font-size: 20px;
  font-weight: bold;
  color: #F1C40F;
}
</style>
