<template>
  <view :style="{ flex: 1, alignItems:'center'}">
    <Header @drawer="openDrawer" :title="title"></Header>
    <view class="calendar-container">
      <!-- load events for each month from the database and use the loadItemsForMonth function to load the events on the agenda -->
    <agenda
      v-bind:items="items"
      :loadItemsForMonth="loadItems"
      :renderItem="renderItem"
      :theme="{
        agendaDayTextColor: 'green',
        agendaDayNumColor: 'green',
        selectedDayBackgroundColor: 'green',
        dotColor: 'green',
        todayTextColor: 'orange',
        agendaTodayColor: 'orange',
        dotColor: 'white',
      }"
    />
    </view>
  </view>
</template>

<script>
import React from "react"
import { Avatar, Card } from "react-native-paper";
import { View, StyleSheet, TouchableOpacity, Text } from "react-native";
import { Agenda } from "react-native-calendars";
import Header from "../components/header";
const timeToString = (time) => {
  var date = new Date(time);
  return date.toISOString().split("T")[0];
};
export default {
  props: {
    navigation: { type: Object },
  },
  data: function() {
    return {
      title:"Calendar",
      CurrentDate: this.dateToString(new Date().toDateString().substring(4)),
      items: {},
      styles: StyleSheet.create({
        item: {
          flexDirection: "row",
          justifyContent: "space-between",
          alignItems: "center",
        },
      }),
    };
  },
  methods: {
    openDrawer: function() {
      this.navigation.openDrawer();
    },
    dateToString: function(time) {
      var vm = this;
      var temp = time.split(" ");
      if (temp[0] == "Jan") {
        vm.CurrentDate = "1";
      } else if (temp[0] == "Feb") {
        vm.CurrentDate = "2";
      } else if (temp[0] == "Mar") {
        vm.CurrentDate = "3";
      } else if (temp[0] == "Apr") {
        vm.CurrentDate = "4";
      } else if (temp[0] == "May") {
        vm.CurrentDate = "5";
      } else if (temp[0] == "Jun") {
        vm.CurrentDate = "6";
      } else if (temp[0] == "Jul") {
        vm.CurrentDate = "7";
      } else if (temp[0] == "Aug") {
        vm.CurrentDate = "8";
      } else if (temp[0] == "Sep") {
        vm.CurrentDate = "9";
      } else if (temp[0] == "Oct") {
        vm.CurrentDate = "10";
      } else if (temp[0] == "Nov") {
        vm.CurrentDate = "11";
      } else if (temp[0] == "Dec") {
        vm.CurrentDate = "12";
      }
      vm.CurrentDate += "-";
      vm.CurrentDate += temp[1];
      vm.CurrentDate += "-";
      vm.CurrentDate += temp[2];
      var result = vm.CurrentDate;
      return result;
    },
    goToHomeScreen() {
      this.navigation.navigate("HomeScreen");
    },
    setItem(item) {
      this.items = item;
    },
    loadItems(day) {
      var vm = this;
      setTimeout(function() {
        for (let i = -15; i < 85; i++) {
          const time = day.timestamp + i * 24 * 60 * 60 * 1000;
          const strTime = timeToString(time);
          if (!vm.items[strTime]) {
            vm.items[strTime] = [];
            const numItems = Math.floor(Math.random() * 3 + 1);
            for (let j = 0; j < numItems; j++) {
              vm.items[strTime].push({
                name: "Item for " + strTime + " #" + j,
                height: Math.max(50, Math.floor(Math.random() * 150)),
              });
            }
          }
        }
        const newItems = {};
        Object.keys(vm.items).forEach((key) => {
          newItems[key] = vm.items[key];
        });
        vm.setItem(newItems);
      }, 1000);
    },
    renderItem(item) {
      return (
        <TouchableOpacity style={{ marginRight: 10, marginTop: 17 }}>
          <Card>
            <Card.Content>
              <View style={this.styles.item}>
                <Text>{item.name}</Text>
                <Avatar.Text label="E" style={{ backgroundColor: "orange" }} />
              </View>
            </Card.Content>
          </Card>
        </TouchableOpacity>
      );
    },
  },
  components: {
    View,
    Agenda,
    StyleSheet,
    React,
    TouchableOpacity,
    Text,
    Avatar,
    Card,
    Header,
  },
};
</script>

<style>
.calendar-container{
  height: 100%;
  width: 100%;
}
</style>
