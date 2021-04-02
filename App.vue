<template>
  <view class="container" v-if="!isLogin">
    <app-navigator></app-navigator>
  </view>
  <view class="image-container" v-else-if="isLogin">
    <image
      :style="{ width: 160, height: 100 }"
      :source="require('./assets/dw.png')"
    />
    <text class="title">Younite360</text>
    <component
      @changepage="changePage"
      @signin="signin"
      @register="register"
      :is="which"
    ></component>
  </view>
</template>

<script>
//navigator
import {
  createAppContainer,
  createStackNavigator,
  createDrawerNavigator,
} from "vue-native-router";

import Login from "./components/Login";
import Register from "./components/Register";

import HomeScreen from "./components/Home";
//import Home from "./screens/home";
import MessagesScreen from "./screens/Messages";
import CalendarScreen from "./screens/Calendar";
import ProfileScreen from "./screens/Profile";
import Header from "./screens/header/HeaderWithButtons";
import YounnectionsScreen from "./screens/Younnections";
import NotificaitonsScreen from "./screens/Notifications";

const DrawerNavigator = createDrawerNavigator(
  {
    //HeaderScreen: Header,
    Home: HomeScreen,
    Messages: MessagesScreen,
    Calendar: CalendarScreen,
    Profile: ProfileScreen,
    Younnections: YounnectionsScreen,
    Notifications: NotificaitonsScreen,
  },
  {
    initialRouteName: "Home",
  }
);
const StackNavigator = createStackNavigator(
  {
    Drawer: {
      screen: DrawerNavigator,
      navigationOptions: {
        title: "Younite360",
        headerStyle: {
          backgroundColor: "green",
        },
        headerTintColor: "yellow",
      },
    },
  },
  {
    initialRouteName: "Drawer",
    headerMode: "none"
  }
);
const AppNavigator = createAppContainer(StackNavigator);

export default {
  name: "App",
  components: {
    Login,
    Register,
    AppNavigator,
  },
  data() {
    return {
      isLogin: true,
      which: Login,
    };
  },
  methods: {
    changePage() {
      this.isLogin = !this.isLogin;
    },
    register() {
      this.which = Register;
    },
    signin() {
      this.which = Login;
    },
  },
};
</script>

<style>
.container {
  flex: 1;
  background-color: white;
}
.circle {
  background-color: yellow;
  height: 1;
  width: 1;
  border-radius: 100;
}
.text-style {
  font-size: 20;
  color: yellow;
}
.nav-bar {
  display: flex;
  justify-content: center;
  height: 50;
  width: 100%;
  background-color: green;
}
.bottom-bar {
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
.image-container {
  flex: 1;
  align-items: center;
  justify-content: center;
  margin-top: 20%;
}
.title {
  color: black;
  font-size: 50;
}
.text-color-primary {
  color: blue;
  font-size: 30;
}
.common {
  background-color: whitesmoke;
}
.search {
  border-radius: 100px;
}
</style>
