<template>
  <view class="container">
    <card class="card-header-container">
    <image-background :source="require('../assets/background.png')" class="background">
        <image class="avatar"
            :source="require('../assets/icons8-user-male-500.png')"
        />
        <view class="info">
            <text class="info-text-name">Bhargav Koritala</text>
            <text class="info-text">bhargavK@example.com</text>
        </view>
        <text class="about-content">Hard-working individual with proficiency in HTML, JavaScript, and CSS, as well as ability to communicate effectively in a team setting.</text>
    </image-background> 
    </card> 
    <touchable-opacity class="clickable-container"> 
    <card class="card-container">
    <view class="section">          
        <image class="icon"
            :source="require('../assets/icons8-school-80.png')"
        />
        <view class="content"> 
            <text class="content-header">School</text>
            <text class="content-detail">University at Buffalo</text>
        </view>       
    </view>
    </card>
    </touchable-opacity>
    <touchable-opacity class="clickable-container">
    <card class="card-container">
    <view class="section">
        <image class="icon"
            :source="require('../assets/icons8-job-seeker-96.png')"
        />
        <view class="content"> 
            <text class="content-header">Occupation</text>
            <text class="content-detail">Full Stack Developer</text>
        </view>
    </view>
    </card>
    </touchable-opacity>
    <touchable-opacity class="clickable-container">
    <card class="card-container">
    <view class="section">
        <image class="icon"
            :source="require('../assets/icons8-development-skill-96.png')"
        />
        
        <view class="content"> 
            <text class="content-header">Skills</text>
            <text class="content-detail">CSS, JavaScript, VueJS</text>
        </view>
    </view>
    </card>
    </touchable-opacity>
  </view>
</template>

<script>
import React from "react";
import { ImageBackground, View,StyleSheet,TouchableOpacity,Text} from "react-native";
import { Card } from 'react-native-paper';
export default {
    props: {
    navigation: { type: Object }
  },
  data() {
    return {
      text:"hello",
      styles: StyleSheet.create({
        item:{flexDirection:'row',
        justifyContent: 'space-between',
        alignItems: 'center'}
      })
    };
  },
  methods: {
       goToHomeScreen() {
      this.navigation.navigate("HomeScreen");
    },
  },
  components:{
      ImageBackground, View,StyleSheet,TouchableOpacity,Text, Card,React
  }
};
</script>

<style>
.container {
  flex: 1;
  width: 100%;
  background-color: #f2f2f2;
  align-items: center;
}
.card-container{
    width: 100%;
    height: 100%;
    align-items: center;
    display: flex;
    flex-direction: row;
}
.clickable-container{
    width: 95%;
    height: 15%;
    margin-top: 1.7%;
}
.card-header-container{
    width: 100%;
    height: 50%;
    align-items: center;
    display: flex;
    flex-direction: row;
}
.text-color-primary {
  color: blue;
  font-size: 30;
}
.avatar{
    height: 130px;
    width: 130px;
    border-radius: 100;
    background-color: rgba(245, 255, 226, 0.322);
    overflow: hidden;
}
.background{
    flex: 1;
    width: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: space-evenly;
}
.info{
    align-items: center;
}
.info-text-name{
    font-size: 24px;
    color: white;
    font-weight: bold;
}
.info-text{
    font-size: 15px;
    color: white;
}
.section{
    flex: 0.15;
    width: 90%;
    margin-top: 10px;
    align-items: center;
    flex-direction: row;
}
.icon{
    width: 30px;
    height: 30px;
    margin: 15px;
}

.content{
    width: 90%;
    height: 35px;
    flex-direction: column;
}
.content-header{
    font-size: 12px;
    font-weight: bold;
}
.content-detail{
    font-size: 15px;
}
.about{
    justify-content: center;
    flex-direction: column;
    flex:0.15;
    width: 100%;
    background-color: rgba(202, 236, 224, 0.651);
}
.about-content{
    color: white;
    padding-left: 5%;
    padding-right: 5%;
    text-align: center;
}

.sections-container{
    flex:0.5;
}
</style>