<template>
  <view class="main-container">
      <Header @drawer="openDrawer" :title="title"></Header>
    <card class="notification-container">
      <view class="header-container">
        <text class="header">Network Notifications</text>
      </view>
      <!-- load network notifications from database and display in the following format and wrap around with scroll-view  -->
      <view class="empty-content-container">
        <text class="notification-text"> No new notifications </text>
      </view>
    </card>

    <card class="notification-container">
      <view class="header-container">
        <text class="header">Younnection Notifications</text>
      </view>
      <!-- load younnection notifications from database and display in the following format -->
      <scroll-view>
        <touchable-opacity class="content">
          <text class="notification-text"
            >Yonnection request from Chin Ya Russell</text
          >
        </touchable-opacity>
        <touchable-opacity class="content">
          <text class="notification-text"
            >Chin Ya Russell accepted your Younnection</text
          >
        </touchable-opacity>
        <touchable-opacity class="content">
          <text class="notification-text"
            >Yonnection request from Shivaleela Hubli</text
          >
        </touchable-opacity>
        <touchable-opacity class="content">
          <text class="notification-text"
            >Shivaleela Hubli accepted your Younnection</text
          >
        </touchable-opacity>
        <touchable-opacity class="content">
          <text class="notification-text">More Notifications</text>
        </touchable-opacity>
      </scroll-view>
    </card>

    <card class="notification-container">
      <view class="header-container">
        <text class="header">Message Notifications</text>
      </view>
      <!-- load message notifications from database and display in the following format -->
      <scroll-view>
        <touchable-opacity class="content">
          <text class="notification-text">Message from Chin Ya Russell</text>
        </touchable-opacity>
      </scroll-view>
    </card>
  </view>
</template>

<script>
import { Card } from "react-native-paper";
import Header from "../components/header";
export default {
  props: {
    navigation: { type: Object },
  },
  data() {
    return {
      title:"Notifications"
    };
  },
  methods: {
    openDrawer: function() {
      this.navigation.openDrawer();
    },
  },
  components: { Header, Card },
};
</script>

<style>
.main-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #f5f5f5e7;
}
.notification-container {
  flex: 1;
  /* height: 27%; */
  width: 95%;
  margin: 2%;
}
.header-container {
  height: 45;
  background-color: green;
  justify-content: center;
  /* flex-direction: row; */
  align-items: center;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
.header {
  font-size: 16px;
  color: #F1C40F;
  font-weight: bold;
  letter-spacing: 0.5px;
}
.empty-content-container {
  align-items: center;
}
.content {
  border-bottom-width: 1;
  border-color: #d9d9d9;
}
.notification-text {
  padding: 9;
  font-size: 15px;
  color: black;
  text-align: center;
}
</style>
