<template>
  <scroll-view>
      <Header @drawer="openDrawer" :title="title"></Header>
        <view class="main"></view>
          <view class="avatar-container">
              <touchable-opacity>
                <view class="avatar-boarder">
                    <image class="avatar" :source="require('../assets/icons8-user-male-500.png')"/>
                </view>
              </touchable-opacity>
              <text class="name-text">Bhargav Koritala</text>
              <text class="email-text">bhargavK@example.com</text>
              <view class="about-section">
                <text class="about-header">About</text>
                <text class="about-text">Hard-working individual with proficiency in HTML, JavaScript, and CSS, as well as ability to communicate effectively in a team setting.</text>
              </view>
            <view class="line"></view>
          </view>
            <view class="info-container">
              <view class="info-header-container">
                  <view class="info-header">
                      <text class="info-text">Education</text>
                      <touchable-opacity>
                      <image class="plus-icon" :source="require('../assets/icons8-plus-96.png')"/>
                      </touchable-opacity>
                  </view>
                  <view class="info-detail">
                      <text class="school-name">University at Buffalo</text>
                      <text class="degree">Master's</text>
                      <text class="major">Computer Science</text>
                      <text class="date">2019 - Present</text>
                  </view>
                  <view class="info-detail">
                      <text class="school-name">Vellore Institute of Technology</text>
                      <text class="degree">Bachelor's</text>
                      <text class="major">Electronics and Communication</text>
                      <text class="date">2013 - 2017</text>
                  </view>
                </view>
                <view class="line"></view>
                <view class="info-header-container">
                  <view class="info-header">
                      <text class="info-text">Work Experience</text>
                      <touchable-opacity>
                      <image class="plus-icon" :source="require('../assets/icons8-plus-96.png')"/>
                      </touchable-opacity>
                  </view>
                  <view class="info-detail">
                      <text class="company-name">Atwick Inc.</text>
                      <text class="job-title">Full Stack Developer Intern</text>
                      <text class="location">Ithaca, NY</text>
                      <text class="date">10/12/2020 - Present</text>
                  </view>
                </view>
                <view class="line"></view>
                <view class="info-header-container">
                  <view class="info-header">
                      <text class="info-text">Skills</text>
                      <touchable-opacity>
                      <image class="plus-icon" :source="require('../assets/icons8-plus-96.png')"/>
                      </touchable-opacity>
                  </view>
                  <view class="skill-tag-container">
                      <view class="skill-tag">
                          <text class="tag-text">HTML</text>
                      </view>
                      <view class="skill-tag">
                          <text class="tag-text">CSS</text>
                      </view>
                      <view class="skill-tag">
                          <text class="tag-text">JavaScript</text>
                      </view>
                      <view class="skill-tag">
                          <text class="tag-text">VueJS</text>
                      </view>
                  </view>
                </view>
            </view>
  </scroll-view>
</template>

<script>
import React from "react";
import { ImageBackground, View,StyleSheet,TouchableOpacity,Text} from "react-native";
import { Card } from 'react-native-paper';
import Header from "../components/header";
export default {
    props: {
    navigation: { type: Object }
  },
  data() {
    return {
      title:"Profile",
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
    openDrawer: function() {
      this.navigation.openDrawer();
    },
  },
  components:{
      ImageBackground, View,StyleSheet,TouchableOpacity,Text, Card,React,Header 
  }
};
</script>

<style>

.main{
    padding: 10px;
    width: 100%;
    background-color: green;
    height: 100px;
}
.avatar{
    height: 140px;
    width: 140px;
    border-radius: 100;
    background-color: white;
    overflow: hidden;
}
.avatar-boarder{
    height: 150px;
    width: 150px;
    border-radius: 100;
    overflow: hidden;
    align-items: center;
    justify-content: center;
    display: flex;
    margin-top: -70px;
}
.avatar-container{
    align-items: center;
    background-color: white;
}
.name-text{
    font-size: 20px;
    font-weight: bold;
    padding: 10px;
}
.email-text{
    font-size: 16px;
    padding-bottom: 15px;
}
.about-header{
    font-size: 16px;
    font-weight: bold;
    width: 100%;
    text-align: left;
}
.about-text{
    text-align: justify;
}
.about-section{
    display: flex;
    padding: 15px;
    width: 90%;
    border-top-color: #c4c4c4;
    border-top-width: 1px;
    border-bottom-color: #c4c4c4;
    border-bottom-width: 1px;
    border-left-color: #c4c4c4;
    border-left-width: 1px;
    border-right-color: #c4c4c4;
    border-right-width: 1px;
    justify-content: center;
    background-color: #f4f4f4;
}
.line{
    width: 90%;
    height: 3px;
    background-color: green;
    margin-top: 15px;
    margin-bottom: 15px;
}
.info-header-container{
    width: 90%;
    display: flex;
    flex-direction: column;
}
.info-header{
    display: flex;
    flex-direction: row;
    align-items: center;
}
.info-text{
    font-size: 16px;
    font-weight: bold;
}
.plus-icon{
    width: 25px;
    height: 25px;
    margin-left: 10px;
}
.info-detail{
    margin-top: 10px;
    padding: 15px;
    border-top-color: #c4c4c4;
    border-top-width: 1px;
    border-bottom-color: #c4c4c4;
    border-bottom-width: 1px;
    border-left-color: #c4c4c4;
    border-left-width: 1px;
    border-right-color: #c4c4c4;
    border-right-width: 1px;
    background-color: #f4f4f4;
}
.info-container{
    width: 100%;
    align-items: center;
    background-color: white;
}
.skill-tag-container{
    margin-bottom: 10px;
    margin-top: 10px;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
}
.skill-tag{
    background-color: green;
    padding: 10px;
    margin: 5px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.tag-text{
    color: white;
    font-weight: bold;
}
</style>