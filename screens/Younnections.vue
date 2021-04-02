<template>
  <view class="main-container">
    <Header @drawer="openDrawer"></Header>
    <card class="manager-container">
      <view class="header-container">
        <image class="icon" :source="require('../assets/manager.png')" />
        <text class="header">Younnections Manager</text>
      </view>
      <view class="manager-group">
        <touchable-opacity class="sections">
          <text class="manager-text">Connections</text>
          <text class="manager-text">101</text>
        </touchable-opacity>
        <touchable-opacity class="sections">
          <text class="manager-text">Groups</text>
          <text class="manager-text">10</text>
        </touchable-opacity>
        <touchable-opacity class="sections">
          <text class="manager-text">Contacts</text>
          <text class="manager-text">165</text>
        </touchable-opacity>
      </view>
    </card>
    <card class="request-container">
      <view class="header-container">
        <image class="icon" :source="require('../assets/request-friend.png')" />
        <text class="header">Requests from younnectors</text>
      </view>
      <view class="request">
        <view class="person">
          <text class="request-person">Chin Ya Russell</text>
          <text class="request-info"
            >Administrative Assistant at Atwick.Inc</text
          >
        </view>
        <view class="btns">
          <touchable-opacity class="accept"
            ><text class="accept-text">Younnect</text></touchable-opacity
          >
          <touchable-opacity class="reject">
            <text class="reject-text">Youject</text></touchable-opacity
          >
        </view>
      </view>
      <view class="request">
        <view class="person">
          <text class="request-person">Shivaleela Hubli</text>
          <text class="request-info">Graduate Student at UB</text>
        </view>
        <view class="btns">
          <touchable-opacity class="accept"
            ><text class="accept-text">Younnect</text></touchable-opacity
          >
          <touchable-opacity class="reject">
            <text class="reject-text">Youject</text></touchable-opacity
          >
        </view>
      </view>
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
    return {};
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
.manager-container {
  height: 27%;
  width: 95%;
  margin-top: 4%;
}
.request-container {
  height: 65%;
  width: 95%;
  margin-top: 4%;
}
.manager-group {
  width: 100%;
  height: 70%;
  justify-content: space-evenly;
}
.header-container {
  height: 45;
  background-color: green;
  justify-content: flex-start;
  flex-direction: row;
  align-items: center;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
.header {
  font-size: 16px;
  color: yellow;
  font-weight: bold;
  letter-spacing: 0.5px;
}
.icon {
  width: 35px;
  height: 35px;
  margin: 15px;
}
.sections {
  background-color: white;
  flex-direction: row;
  justify-content: space-between;
}
.manager-text {
  padding: 8;
  font-size: 15px;
  color: black;
}
.request {
  flex-direction: row;
  justify-content: space-between;
  border-bottom-width: 1;
  border-bottom-color: #d9d9d9;
  margin-bottom: 5px;
}
.person {
  margin: 10px;
  flex-direction: column;
}
.btns {
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
  width: 35%;
}
.request-person {
  font-size: 15px;
  font-weight: bold;
  padding-bottom: 5px;
}
.request-info {
  font-size: 10px;
  padding-bottom: 5px;
}
.accept {
  /* border-bottom-width: 1;
    border-bottom-color: green;
    border-top-width: 1;
    border-top-color: green;
    border-left-width: 1;
    border-left-color: green;
    border-right-width: 1;
    border-right-color: green; */
  background-color: #00b300;
  border-radius: 5px;
}
.accept-text {
  color: white;
  font-size: 14px;
  padding: 4px;
}
.reject {
  background-color: #ff471a;
  border-radius: 5px;
}
.reject-text {
  color: white;
  font-size: 14px;
  padding: 4px;
}
</style>
