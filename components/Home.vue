<template>
    <view class="bottom-bar">
      <touchable-opacity :on-press="gotoYounnections">
        <text class="text-style">Younnections</text>
      </touchable-opacity>
      <touchable-opacity :on-press="gotoMessages">
        <text class="text-style">Messages</text>
      </touchable-opacity>
      <touchable-opacity :on-press="gotoNotifications">
        <text class="text-style">Notifications</text>
      </touchable-opacity>
    </view>
</template>

<script>
export default {
  props: {
    navigation: { type: Object }
  },
  data() {
    return {
    };
  },
  methods: {
    gotoYounnections: function(){
      this.navigation.navigate("YounnectionsScreen");
    },
    gotoMessages: function(){
      this.navigation.navigate("MessagesScreen");
    },
    gotoNotifications: function(){
      this.navigation.navigate("NotificationsScreen");
    },
  },
};
</script>

<style>
.nav-bar{
  display: flex;
  justify-content: center;
  height: 50;
  width: 100%;
  background-color: green;
}
.bottom-bar{
  position: absolute;
  bottom: 0;  
  height: 50;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-direction: row;
  background-color: green;
}
.text-style{
  font-size: 20;
  color: yellow;
}
</style>