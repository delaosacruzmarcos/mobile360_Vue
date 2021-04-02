<template>
<view>
<view class="nav-bar">
  <Header @drawer="openDrawer" :title="title"></Header>
</view>
<image-background :source="require('../assets/background.png')" class="background">
        <image class="avatar"
            :source="require('../assets/ww.png')"
        />
    </image-background> 
   <touchable-opacity class="content">
          <text class="notification-text">welcome to the homepage (possible custom graphic)
          </text>
        </touchable-opacity>
  <view class="bottom-bar">
    <touchable-opacity :on-press="gotoYounnections">
      <text class="text-style">Younnections</text>
    </touchable-opacity>
    <touchable-opacity :on-press="gotoMessages">
      <text class="text-style">Messages</text>
    </touchable-opacity>
    <touchable-opacity :on-press="gotoNotifications">
      <text class="text-style">Calendar</text>
    </touchable-opacity>
  </view>
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
import { ImageBackground, View,StyleSheet,TouchableOpacity,Text} from "react-native";
import { Card } from 'react-native-paper';
export default {
  props: {
    navigation: { type: Object },
  },
  data() {
    return {
      title:"Home"
    };
  },
  methods: {
    gotoYounnections: function() {
      this.navigation.navigate("Younnections");
    },
    gotoMessages: function() {
      this.navigation.navigate("Messages");
    },
    gotoNotifications: function() {
      this.navigation.navigate("Calendar");
    },
    openDrawer: function() {
      this.navigation.openDrawer();
    },
  },
  components: { Header },
};
</script>

<style>
.nav-bar {
  display: flex;
  justify-content: center;
  height: 80;
  width: 100%;
  background-color: green;
}
.bottom-bar {
  position: relative;
  bottom: 0;
  height: 50;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-direction: row;
  background-color: green;
}
.text-style {
  font-size: 20;
  color: yellow;
}
.content {
  border-bottom-width: 1;
  border-color: #d9d9d9;
  padding: 100;
}
.homePage-text {
  padding: 0;
  font-size: 30px;
  color: black;
  text-align: center;
}
.card-header-container{
    width: 100%;
    height: 43%;
    align-items: center;
    display: flex;
    flex-direction: row;
}
.background{
    flex: 1;
    width: 100%;
    height: 200%;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: space-evenly;
}
.avatar{
    height: 130px;
    width: 130px;
    border-radius: 100;
    background-color: rgba(245, 255, 226, 0.322);
    overflow: hidden;
}

</style>
