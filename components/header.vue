<template>
<view class="header-container">
  <touchable-opacity :on-press="openDrawer">
    <image class="icon" :source="require('../assets/menu-icon.png')" />
  </touchable-opacity>
  <text class="header-title">{{title}}</text>
</view>
</template>

<script>
import { Alert } from 'react-native';
export default {
  props: {
    navigation: { type: Object },
    title: String
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
.header-container{
  padding-top: 5%;
  align-items: center;
  flex-direction: row;
}
.icon {
  width: 35px;
  height: 35px;
  margin-right: 5%;
}
.header-title{
  font-size: 16px;
  font-weight: bold;
}
</style>
