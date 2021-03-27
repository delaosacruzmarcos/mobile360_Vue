<template>
      <view class="container">
        <flat-list :data="Messages" :keyExtractor="item => item.id"
           :render-item="(item) => renderList(item)"/>
      </view>
</template>

<script>
import React from "react";
import {StyleSheet, Text, TouchableOpacity, View, FlatList, Button, Image} from "react-native";

export default {
  props: {
    navigation: { type: Object }
  },
  data() {
    return {
      Messages: [
        {
          id: '1',
          userName: 'Chin Ya Russell',
          userImg: require('../assets/user.png'),
          messageTime: '4 mins ago',
          messageText:
          'Hey there, this is my test for a post of my social app in React Native.',
        },
        {
          id: '2',
          userName: 'Sejal Agarwal',
          userImg: require('../assets/user.png'),
          messageTime: '2 hours ago',
          messageText:
          'Hey there, this is my test for a post of my social app in React Native.',
        },
      ],
      styles: StyleSheet.create({
      card: {
        width: '100%'
      },
      userInfo:{
        flexDirection: 'row',
        justifyContent: 'space-between'
      },
      userImgWrapper:{
        paddingTop: 15,
        paddingBottom: 15
      },
      userImg:{
        width:50,
        height:50
      },
      textSection:{
        flexDirection: 'column',
        justifyContent: 'center',
        padding: 15,
        paddingLeft: 0,
        marginLeft: 10,
        width: 300,
        borderBottomWidth: 1,
        borderBottomColor: '#cccccc'
      },
      userInfoText:{
        flexDirection: 'row',
        justifyContent: 'space-between',
        marginBottom: 5,
      },
      userName:{
        fontSize: 14,
        fontWeight:'bold',
      },
      postTime:{
        fontSize:12,
        color:"#666",
      },
      messageText:{
        fontSize:14,
      }
      }),
    };
  },
  methods: {
      goToHomeScreen() {
      this.navigation.navigate("HomeScreen");
    },
      goToChat() {
      this.navigation.navigate("HomeScreen");
    },
    renderList: function(item) {
     return (
      <TouchableOpacity style={this.styles.card} onPress={this.goToChat}>
        <View style={this.styles.userInfo}>
          <View style={this.styles.userImgWrapper}>
            <Image source={item.item.userImg}/>
          </View>
          <View style={this.styles.textSection}>
            <View style={this.styles.userInfoText}>
              <Text style={this.styles.userName}>{item.item.userName}</Text>
              <Text style={this.styles.postTime}>{item.item.messageTime}</Text>
            </View>
            <Text style={this.styles.messageText}>{item.item.messageText}</Text>
          </View>
        </View>
      </TouchableOpacity>
       )
    }
  },
  components: {
   StyleSheet, Text, View, FlatList, Button, TouchableOpacity, Image, React
  }
};
</script>

<style>
.container {
  flex: 1;
  padding-left: 20px;
  padding-right: 20px;
  align-items: center;
  background-color: #ffffff;
}
</style>