<template>
  <view class="container">
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
    <view class="section">
        <image class="icon"
            :source="require('../assets/icons8-school-80.png')"
        />
        <view class="content"> 
            <text class="content-header">School</text>
            <text class="content-detail">University at Buffalo</text>
        </view>
    </view>
    <view class="section">
        <image class="icon"
            :source="require('../assets/icons8-job-seeker-96.png')"
        />
        <view class="content"> 
            <text class="content-header">Occupation</text>
            <text class="content-detail">Full Stack Developer</text>
        </view>
    </view>
    <view class="section">
        <image class="icon"
            :source="require('../assets/icons8-development-skill-96.png')"
        />
        
        <view class="content"> 
            <text class="content-header">Skills</text>
            <text class="content-detail">CSS, JavaScript, VueJS</text>
        </view>
    </view>
  </view>
</template>

<script>
import { ImageBackground, StyleSheet } from "react-native";
export default {
    props: {
    navigation: { type: Object }
  },
  data() {
    return {
      message: "Profile page"
    };
  },
  methods: {
       goToHomeScreen() {
      this.navigation.navigate("HomeScreen");
    }
  },
  components:{
      ImageBackground, StyleSheet
  }
};
</script>

<style>
.container {
  flex: 1;
  width: 100%;
  background-color: white;
  align-items: center;
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
    flex: 0.50;
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
</style>